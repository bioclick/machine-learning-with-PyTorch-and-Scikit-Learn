# Chapter 12: Parallelism

## What is Parallelism
Parallelizing neural network training can significantly speed up the process, allowing you to train larger models or use larger datasets more efficiently. PyTorch provides several tools to help you parallelize neural network training across multiple GPUs. Here are some of the primary methods you can use:

## Data Parallelism
Data parallelism involves splitting the training data across multiple GPUs, where each GPU processes a portion of the input data simultaneously. PyTorch provides a simple way to implement this via the **DataParallel** module.

### How to Use DataParallel
Once you have defined your model, you can wrap it in a **DataParallel** layer. PyTorch will then automatically distribute the data across the GPUs and collect the results.
```python
import torch
import torch.nn as nn

model = MyModel()  # Define your model
if torch.cuda.device_count() > 1:
    model = nn.DataParallel(model)
model.to(torch.device("cuda"))
```

## Model Parallelism
Model parallelism involves splitting the model itself across multiple GPUs, where different GPUs handle different parts of the model. This is useful when the model is too large to fit into the memory of a single GPU.

### How to Use Model Parallelism
Define which parts of your model will be executed on which GPUs. This is a manual process where you need to specify the device for each part of the model.
```python
class MyModel(nn.Module):
    def __init__(self):
        super(MyModel, self).__init__()
        self.part1 = nn.Sequential(
            nn.Linear(1000, 500),
            nn.ReLU(),
        ).to('cuda:0')  # First GPU

        self.part2 = nn.Sequential(
            nn.Linear(500, 100),
            nn.ReLU(),
        ).to('cuda:1')  # Second GPU

    def forward(self, x):
        x = self.part1(x)
        x = x.to('cuda:1')  # Move output of part1 to GPU where part2 is located
        x = self.part2(x)
        return x
```

## Distributed Data Parallel (DDP)
For training on multiple nodes (each with possibly multiple GPUs), PyTorch offers the Distributed Data Parallel (DDP) module, which is more efficient than DataParallel for multi-GPU/multi-node setups.

### How to Use DDP
Let's say we have this sample **train.py** file as it is below:
```python
import torch
import torch.distributed as dist
from torch.nn.parallel import DistributedDataParallel as DDP
import torch.multiprocessing as mp

def main(rank, world_size):
    # Initialize the distributed environment.
    dist.init_process_group("nccl", rank=rank, world_size=world_size)
    torch.cuda.set_device(rank)

    # Model and optimizer
    model = torch.nn.Linear(10, 10).cuda(rank)
    ddp_model = DDP(model, device_ids=[rank])

    # Example training loop
    optimizer = torch.optim.SGD(ddp_model.parameters(), lr=0.01)
    for epoch in range(10):
        optimizer.zero_grad()
        outputs = ddp_model(torch.randn(20, 10).cuda(rank))
        labels = torch.randn(20, 10).cuda(rank)
        loss_fn = torch.nn.MSELoss()
        loss_fn(outputs, labels).backward()
        optimizer.step()

    dist.destroy_process_group()

if __name__ == "__main__":
    world_size = torch.cuda.device_count()
    mp.spawn(main, args=(world_size,), nprocs=world_size, join=True)
```
To execute this python file, use the command below:
```bash
python -m torch.distributed.launch --nproc_per_node=<NUM_GPUS> --nnodes=<NUM_NODES> --node_rank=<NODE_RANK> --master_addr=<MASTER_NODE_IP> --master_port=<MASTER_PORT> train.py
```
Where:
- **--nproc_per_node:** Number of processes to run on each node (usually set to the number of GPUs per node).
- **--nnodes:** Total number of nodes participating in the training.
- **--node_rank:** The rank of the current node starting from 0.
- **--master_addr:** The IP address of the master node (the node with node_rank=0).
- **--master_port:** A free port on the master node for handling communications.