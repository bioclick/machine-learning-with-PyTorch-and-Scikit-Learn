# Chapter 1: Machine Learning Overview

## What is Machine Learning

Machine learning is a branch of artificial intelligence that focuses on creating systems that can learn and make decisions without being explicitly programmed. Instead of following a fixed set of rules, these systems analyze patterns in data, learn from those patterns, and use what they learn to make predictions or decisions. For instance, a machine learning model can identify spam emails by studying past examples or recommend movies by learning your viewing preferences. Essentially, it's like teaching computers to recognize patterns and solve problems on their own.


## Algorithms
In machine learning, algorithms are often divided into three main categories: supervised, unsupervised, and reinforcement learning. 

### 1. Supervised Learning
In supervised learning, the model is trained on a labeled dataset, which means that each training example comes with the correct output. The goal is to learn the relationship between the input data and the output labels so that the model can predict the correct output for new, unseen data. For instance, if we're training a model to recognize cats and dogs in images, each training image would be labeled as either "cat" or "dog." After training, the model can then classify new images.

### 2. Unsupervised Learning
In unsupervised learning, the model is given data without labeled outcomes. Instead, it tries to identify patterns and relationships within the data on its own. For example, clustering algorithms can group similar data points together based on their characteristics, like grouping customers with similar shopping habits. Another example is dimensionality reduction, which simplifies data by identifying the most important features.

### 3. Reinforcement Learning
In reinforcement learning, an agent learns by interacting with an environment and receiving rewards or penalties based on its actions. The goal is to maximize the cumulative reward over time. Unlike supervised learning, the agent is not given direct labels indicating the correct action to take. Instead, it must explore and discover which actions lead to the highest rewards. An example would be training a robot to navigate a maze, where it receives positive rewards for reaching the exit and penalties for hitting walls. Over time, it learns to navigate the maze effectively using this feedback.

### Summary:
- Supervised Learning: Uses labeled data, learns the relationship between inputs and known outputs (e.g., classification, regression).
- Unsupervised Learning: Uses unlabeled data, discovers hidden patterns or structures (e.g., clustering, dimensionality reduction).
- Reinforcement Learning: Learns by trial and error through rewards and penalties, aiming to maximize cumulative rewards.


## Feature Engineering
Feature engineering is the process of transforming raw data into meaningful inputs for machine learning models. It can significantly influence the performance of models. Key steps are listed below:

### 1. Feature Selection
Identifying and choosing the most relevant features reduces noise and computational cost. Techniques like Recursive Feature Elimination (RFE) and feature importance from tree models help select useful features.

### 2. Feature Transformation
Raw data often needs to be standardized, normalized, or encoded to fit model requirements. For instance:
- Normalization: Scaling features to a range, usually between 0 and 1.
- Standardization: Centering features to a mean of 0 and a standard deviation of 1.
- Encoding Categorical Variables: One-hot encoding and label encoding.

### 3. Feature Creation
Sometimes, new features can be generated from existing ones. For example:
- Extracting the year, month, and day from a timestamp.
- Creating interaction terms between features.

## Model Evaluation and Validation
Evaluating and validating models is crucial to ensure they generalize well to unseen data. There are various methods for doing so:

### 1. Train-Test Split
The dataset is split into training and testing sets. The training set is used to train the model, and the testing set evaluates its performance.

### 2. Cross-Validation
There are numerous Cross-Validation methods but one that is commonly used is K-fold. All the other ones are somehow a derivatives of this method. K-fold cross-validation divides data into K parts. The model trains on K-1 parts and validates on the remaining part, repeating this K times. This method gives a more reliable estimate of model performance.

### 3. Evaluation Metrics
Different problems require different metrics for evaluation:

- Classification
  - Accuracy: Percentage of correctly classified instances.
  - Precision: Correctly predicted positives out of all predicted positives.
  - Recall: Correctly predicted positives out of all actual positives.
  - F1-score: Harmonic mean of precision and recall.
  - ROC-AUC: Area Under the ROC Curve, indicating model discrimination.

- Regression
  - Mean Squared Error (MSE): Average squared differences between predicted and actual values.
  - Mean Absolute Error (MAE): Average absolute differences between predicted and actual values.
  - R² (Coefficient of Determination): Proportion of variance explained by the model.


### 4. Overfitting and Underfitting

