# Welcome To The Machine Learning World! 👋
![alt text](./assets/ml_image.png)

## Introduction
Here we want to start a journey and learn everything from sctrach. Therefore, no need to worry about not having a robust backgroung in this field of study.

We are using [this repo](https://github.com/rasbt/machine-learning-book) as our reference. For further information, you can read the book they have provided. Below, you find a list of contents we are about to cover. Commence the exploration to become hero from zero 😎.

## Table of Contents
1. [Chapter 1:](./chapters/01-Machine-Learning-Overview/README.md) Machine Learning Overview
2. [Chapter 2:](./chapters/02-Training/README.md) Training
3. [Chapter 3:](./chapters/03-Classification/README.md) Classification
4. [Chapter 4:](./chapters/04-Pre-Processing/README.md) Pre-Processing
5. [Chapter 5:](./chapters/05-Data-Compression/README.md) Data Compression
6. [Chapter 6:](./chapters/06-Model-Evaluation/README.md) Model Evaluation
7. [Chapter 7:](./chapters/07-Ensemble-Learning/README.md) Ensemble Learning
8. [Chapter 8:](./chapters/08-Sentiment-Analysis/README.md) Sentiment Analysis
9. [Chapter 9:](./chapters/09-Regression/README.md) Regression
10. [Chapter 10:](./chapters/10-Clustering/README.md) Clustering
11. [Chapter 11:](./chapters/11-Multi-Layer-Neural-Network/README.md) Multi-Layer Neural Network
12. [Chapter 12:](./chapters/12-Parallelization/README.md) Parallelization
13. [Chapter 13:](./chapters/13-PyTorch-In-Depth/README.md) PyTorch In-Depth
14. [Chapter 14:](./chapters/14-CNN/README.md) CNN
15. [Chapter 15:](./chapters/15-RNN/README.md) RNN
16. [Chapter 16:](./chapters/16-Transformers/README.md) Transformers
17. [Chapter 17:](./chapters/17-GAN/README.md) GAN
18. [Chapter 18:](./chapters/18-GNN/README.md) GNN
19. [Chapter 19:](./chapters/19-RL/README.md) RL

## Installation
For this project, we are using Ubuntu; thus, all the installation commands are ubuntu based. You can find the equivalant commands for Windows or MacOS if you prefer using those operating systems. 

### First of all, install python if you do not have it already:
```bash
sudo apt update
sudo apt install python3
```

### Next, is installing pip, a package manager for python libraries:
```bash
sudo apt install python3-pip
```

### Create Symbolic Links for python and pip (Optional)
You can use symbolic links to change python3 to python, and pip3 to pip. The purpose is to make it easier to use.
```bash
sudo ln -s /usr/bin/python3 /usr/bin/python
sudo ln -s /usr/bin/pip3 /usr/bin/pip
```

### Let's set up a virtual environment for our codes. Virtual environments help us to have an isolated workspace for each one of our projects. Follow the instructions below:

Installation:
```bash
sudo apt install python3-venv
```

Creating an environment named myenv:
```bash
python3 -m venv myenv
```

Then, we need to activate the environment we have created previously:
```bash
source myenv/bin/activate
```

Whenever you want to exit this environment, simply type this command to deactivate it:
```bash
deactivate
```

### An alternative approach for environment management using mamba (Optional)
At first, we need to install Miniconda:
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

Make the installer executable:
```bash
chmod +x Miniconda3-latest-Linux-x86_64.sh
```

Execute the installer:
```bash
./Miniconda3-latest-Linux-x86_64.sh
```

After the installation, execute this command to apply changes:
```bash
source ~/.bashrc
```

Install mamba:
```bash
conda install mamba -n base -c conda-forge
```

Create an environment using mamba:
```bash
mamba create -n myenv
```

Activate the environment we have created previously, but before that, execute these two commands:
```bash
mamba init
source ~/.bashrc
```

Then, proceed with the activation:
```bash
mamba activate myenv
```

Whenever you want to exit this environment, simply type this command to deactivate it:
```bash
deactivate
```

### Dependencies for ML projects
There are some popular python packages that are commonly used when dealing with ML problems. The instruction for installing them is below:
```bash
pip install numpy scipy matplotlib scikit-learn pandas
```
Moreover, we are going to use [PyTorch](https://pytorch.org/) and some other related packages in this tutorial. You can install them by this command:
```bash
pip install torch torchvision
```