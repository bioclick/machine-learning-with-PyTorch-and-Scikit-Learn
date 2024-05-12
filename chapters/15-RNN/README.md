# Chapter 15: Recurrent Neural Network (RNN)

## What is RNN
![RNN](../../assets/rnn.png)

A Recurrent Neural Network (RNN) is a type of neural network that is particularly suited for sequence prediction problems. RNNs are used extensively in natural language processing (NLP) and other applications where the input data is sequential, such as time series analysis, music generation, and more.

## Core Concept of RNNs
The fundamental feature of an RNN is its ability to maintain a 'memory' of previous inputs in its internal state, which influences the network's output and allows it to exhibit dynamic temporal behavior. 

## Architecture of RNNs
- **Input Layer:** Receives sequences of inputs over time.
- **Hidden Layer:** Maintains hidden states where the RNN does its computations. The hidden state at each time step is updated based on both the current input and the previous hidden state.
- **Output Layer:** Produces the output for each time step, which can depend on the current hidden state or, in some applications, only the last hidden state after processing the entire sequence.

## How RNNs Work
In an RNN, each neuron or unit has a loop that allows information to be passed from one step of the network to the next. This loop acts as a form of memory.

## Variants of RNNs
- **LSTM (Long Short-Term Memory):** LSTMs are designed to handle the vanishing gradient problem by introducing a complex architecture with gates that regulate the flow of information. They have mechanisms to add or remove information to the cell state, regulated by structures called gates.
- **GRU (Gated Recurrent Unit):** GRUs simplify the LSTM design by combining the forget and input gates into a single "update gate". They also merge the cell state and hidden state, and some gating mechanisms, making them less computationally intensive while still capable of capturing long-range dependencies.
