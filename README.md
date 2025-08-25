# Aspect-Based-Sentimental-Analysis

This project investigates different neural network architectures for Aspect-Based Sentiment Analysis (ABSA). Unlike traditional sentiment analysis that provides an overall score, ABSA identifies sentiments towards specific aspects (e.g., food, service, price) within text.

We implement and evaluate three Bi-LSTM based model variants, including an attention-enhanced Bi-LSTM, which allows the model to focus on aspect-relevant words in a sentence.

### Methodology

We designed three Bi-LSTM model variants:

### Variant 1 – Aspect-Augmented Input

Aspect embeddings are appended to word embeddings.

Input sequence is fed into a Bi-LSTM → Softmax for sentiment classification.

### Variant 2 – Aspect-Weighted Hidden Layers

Sentence embeddings processed through Bi-LSTM.

Hidden states concatenated with aspect embeddings → Softmax output.

### Variant 3 – Bi-LSTM with Attention (Main Model)

Aspect embeddings are combined with word embeddings.

The sequence is passed through a Bi-LSTM.

An attention layer computes weights over hidden states, highlighting words most relevant to the given aspect.

Attention-weighted hidden states are aggregated → Softmax classifier.


### Implementation Details
Preprocessing

Removed punctuation, tokenization, lowercasing

Lemmatization applied

Stopwords: customized (negative words like not, never retained)

Embeddings: Pre-trained GloVe (50-dim) vectors

### Hyperparameters (final chosen values)

Layers: 2

Hidden Size: 128

Dropout: 0.5

Learning Rate: 0.01

Optimizer: Adam

Loss: CrossEntropy
