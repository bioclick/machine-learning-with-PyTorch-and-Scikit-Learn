# Chapter 2: Training

In this chapter, we are going to learn what **"Training"** is by an example associated with perceptron. But first:

## What is Perceptron
![PC](../../assets/perceptron.jpg)

A perceptron is a fundamental building block in machine learning, particularly in binary classification tasks. It's a simplified model of a biological neuron, taking multiple inputs, applying weights to each, summing them up, and passing the result through an activation function to produce an output. The perceptron learns by adjusting its weights based on the errors in its predictions, aiming to minimize them during training. While limited to linearly separable problems and prone to convergence issues, perceptrons serve as the basis for more complex neural network architectures, contributing to the foundation of modern deep learning.

## Dataset
We have used the famous Iris dataset which is available [here](https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data). Here is a snippet of this dataset after loading it in a dataframe:

![Ir](../../assets/Iris.png)

## Adaptive Linear Neurons (Adaline)
![Ad](../../assets/Adaline.png)

Adaptive Linear Neurons (Adaline) are similar to perceptrons but use a linear activation function instead of a step function. They adjust their weights iteratively using the gradient descent algorithm to minimize a cost function, typically the sum of squared errors. Convergence in Adaline refers to the stabilization of weights, signifying that further iterations won't significantly change them. This ensures that Adaline finds optimal or near-optimal weights to minimize prediction errors.

Figure down here depicts the difference between perceptrons and Adaline:

![PA](../../assets/perceptron_vs_Adaline.png)






