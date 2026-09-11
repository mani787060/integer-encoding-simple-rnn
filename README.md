# Integer Encoding with SimpleRNN

## Overview

This project demonstrates how **text data can be converted into integer sequences** before being passed to a Recurrent Neural Network (RNN).

Using a small collection of simple text sentences, the notebook explores **tokenization, vocabulary creation, integer encoding, and sequence representation**. These steps form an important part of the preprocessing pipeline for NLP tasks using RNNs.

The project serves as a beginner-friendly introduction to how textual information is converted into numerical form that a neural network can understand.

---

## Objective

* Understand text preprocessing for RNNs
* Learn how tokenization works
* Convert words into integer IDs
* Understand vocabulary and word-index mapping
* Represent sentences as sequences of integers
* Prepare text data for a SimpleRNN model
* Understand the connection between NLP preprocessing and RNN architectures

---

## Dataset

The notebook uses a small custom dataset containing short sentences:

```python
docs = [
    'go india',
    'india india',
    'hip hip hurray',
    'jeetega bhai jeetega india jeetega',
    'bharat mata ki jai',
    'kohli kohli',
    'sachin sachin',
    'dhoni dhoni',
    'modi ji ki jai',
    'inquilab zindabad'
]
```

The dataset contains repeated words and short sentences, making it useful for demonstrating vocabulary creation and integer encoding.

---

## What is Integer Encoding?

Neural networks cannot directly understand raw text. Therefore, words are first converted into numerical IDs.

For example:

```text
"india" → 2
"bharat" → 5
"kohli" → 8
```

The exact integer assigned to each word depends on the vocabulary generated during preprocessing.

A sentence such as:

```text
"india india"
```

can therefore be represented as:

```text
[2, 2]
```

These integer sequences can then be used as input to an embedding layer and eventually an RNN.

---

## Workflow

```text
Raw Text
   ↓
Tokenization
   ↓
Vocabulary Creation
   ↓
Word → Integer Mapping
   ↓
Integer Sequences
   ↓
Sequence Preparation
   ↓
SimpleRNN
```

---

## Key Concepts Covered

### 1. Tokenization

Tokenization breaks text into individual words or tokens.

```text
"bharat mata ki jai"
        ↓
["bharat", "mata", "ki", "jai"]
```

### 2. Vocabulary

The unique words in the dataset form the vocabulary.

Each word receives a numerical index.

### 3. Integer Encoding

Each word is replaced by its corresponding integer index.

```text
"bharat mata ki jai"
        ↓
[integer, integer, integer, integer]
```

### 4. Sequence Representation

Every sentence becomes a numerical sequence that can be processed by neural networks.

---

## Why Integer Encoding is Important

Machine learning models work with numerical values rather than raw text. Integer encoding provides a simple way to represent words numerically before applying further NLP processing.

However, integer IDs themselves do **not** represent semantic similarity. For example, an ID of `5` is not necessarily more meaningful or similar to an ID of `6`.

For this reason, integer sequences are commonly followed by an **Embedding layer**, which learns meaningful vector representations of words.

---

## Technologies Used

* Python
* TensorFlow
* Keras
* NLP preprocessing
* SimpleRNN

---

## Key Learnings

* Text must be converted into numerical representations before being used by neural networks.
* Tokenization converts text into individual tokens.
* Integer encoding maps tokens to numerical IDs.
* Different sentences can have different sequence lengths.
* Integer encoding is generally an intermediate preprocessing step rather than the final representation used by an RNN.
* Embedding layers can convert integer IDs into dense vector representations.
* Proper text preprocessing is an important foundation for NLP and sequence modeling.

---

## Future Improvements

This basic project can be extended by:

* Adding a Keras `Embedding` layer
* Applying padding to make sequences equal in length
* Building a complete SimpleRNN classification model
* Comparing integer encoding with one-hot encoding
* Experimenting with different vocabulary sizes
* Using larger NLP datasets
* Comparing SimpleRNN with LSTM and GRU
* Adding text classification or sentiment analysis

---

## Conclusion

This project provides a simple introduction to **integer encoding for NLP and RNNs**. It demonstrates how raw sentences can be tokenized, converted into integer sequences, and prepared for processing by neural networks.

Understanding this preprocessing step is important before moving toward **Embedding layers, SimpleRNN, LSTM, GRU, and more advanced NLP architectures**.
