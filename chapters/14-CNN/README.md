# Chapter 14: Convolutional Neural Network (CNN)

## What is CNN
![CNN](../../assets/cnn.jpg)

Convolutional Neural Networks (CNNs) are a class of deep neural networks that are particularly powerful for tasks involving image data, though they are also used for other types of sequential data like audio and text. CNNs have been revolutionary in the field of computer vision, enabling breakthroughs in applications such as image classification, object detection, face recognition, and more.

## Core Components of CNNs
**1. Convolutional Layers:**
- These layers apply a set of learnable filters (or kernels) to the input image. Each filter in a convolutional layer is small spatially (along width and height), but extends through the full depth of the input volume. 
- As the filter slides (or convolves) across the image, it produces a 2D activation map that gives the responses of that filter at every spatial position.

**2. Pooling (Subsampling or Down-sampling) Layers**
- These layers reduce the spatial size of the representation to decrease the amount of parameters and computation in the network
- Common types of pooling include max pooling and average pooling.

**3. Activation Layer**
- This layer will apply an elementwise activation function, such as the rectified linear activation function. This layer does not change the size of its input.
- The purpose of the activation function is to introduce non-linear properties to the system, which enables the network to learn more complex functions.

**4. Fully Connected Layers**
- After several convolutional and pooling layers, the high-level reasoning in the neural network is done via fully connected layers. 
- Neurons in a fully connected layer have connections to all activations in the previous layer, as seen in regular Neural Networks. Their activations can hence be computed with a matrix multiplication followed by a bias offset.


## Dataset
We used the CelebA dataset. You can download this dataset from [here](https://drive.google.com/file/d/1m8-EBPgi5MRubrm6iQjafK2QMHDBMSfJ/view?usp=sharing). 

Moreover, we have used the famous MNIST dataset which is available [here](http://yann.lecun.com/exdb/mnist/). Here is a snippet of this dataset after loading it:

![MN](../../assets/MNIST.png)

