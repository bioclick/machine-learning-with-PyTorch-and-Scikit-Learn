# Chapter 8: Sentiment Analysis

## What is Sentiment Analysis
Sentiment analysis, also known as opinion mining, is a natural language processing (NLP) technique used to determine and classify the sentiment or emotional tone behind a series of words. The goal is to identify whether the sentiment is positive, negative, neutral, or falls into other predefined categories. This technique is widely used to analyze text data, especially from social media, reviews, and surveys.

## How Sentiment Analysis Works
**1. Text Preprocessing**
- **Tokenization:** Splitting text into words or sentences.
- **Lowercasing:** Converting all characters to lowercase.
- **Stopword Removal:** Removing common words like "and," "the," etc.
- **Stemming/Lemmatization:** Reducing words to their root form.

**2. Feature Extraction**
- **Bag of Words (BoW):** Representing text based on word frequency.
- **TF-IDF (Term Frequency-Inverse Document Frequency):** Weighing words based on their importance in a document.
- **Word Embeddings:** Dense vector representations like Word2Vec, GloVe, or FastText.
- **Pre-trained Models:** Using representations like BERT, GPT, or other large language models.

**3. Sentiment Classification Approaches**
- **Lexicon-Based Methods:**
  - Uses predefined dictionaries of positive and negative words.
  - Example lexicons: SentiWordNet, VADER, TextBlob.

- **Machine Learning-Based Methods:**
  - Supervised learning using labeled datasets.
  - Common models: Naive Bayes, Support Vector Machines (SVM), Logistic Regression.

- **Deep Learning-Based Methods:**
  - Neural networks like CNNs, RNNs, LSTMs, and attention mechanisms.
  - Transformers (e.g., BERT) for state-of-the-art performance.

- **Hybrid Approaches:**
  - Combines lexicon-based and machine learning-based methods.

**4. Evaluation Metrics**
- $Accuracy = \frac{TP+TN}{TP+TN+FP+FN}$
- $Precision = \frac{TP}{TP + FP}$
- ROC-AUC: Area under the ROC curve for classification performance.


## Dataset
We have used an IMDB dataset which is available [here](https://ai.stanford.edu/~amaas/data/sentiment/). Or you can simply download it with a python code provided in the [nootebook of this chapter](./ch08.ipynb).
