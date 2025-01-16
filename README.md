# Arabic Poetry Generation: Deep Learning for Poetry Synthesis

This project explores the use of **deep learning** techniques, including **LSTMs** and **Word2Vec**, for **Arabic poetry synthesis**. Text generation, especially poetry synthesis, is a promising yet challenging AI task. This code is an attempt to replicate the results of the paper With added improvements:  
**Arabic Text Generation: Deep Learning for Poetry Synthesis**  
[ResearchGate Publication](https://www.researchgate.net/publication/349802531_Arabic_Text_Generation_Deep_Learning_for_Poetry_Synthesis)

---

## Table of Contents
1. [Overview](#overview)
2. [Dataset](#dataset)
3. [Methodology](#methodology)

---

## Overview
Arabic poetry holds immense cultural significance, but it is facing a decline in engagement. This project uses deep learning models to generate Arabic poetry that is fluent, authentic, and creative. We explore the use of **LSTMs** and **Word2Vec** for text generation, focusing on forward and backward word training with varying sequence lengths. The model is trained on a subset of two large Arabic poetry datasets due to hardware limitations.

---

## Dataset
Two datasets of Arabic poems were used:
1. **[Arabic Poetry Dataset)](https://www.kaggle.com/datasets/fahd09/arabic-poetry-dataset-478-2017)** from Kaggle. **(I've been working on this dataset)**
2. **Alqasidah.com**: A collection of Arabic poems.

### Preprocessing
- Removed diacritics, punctuation, and incorrect words.
- Handled numbers and non-vocabulary words.
- Tagged unknown words with `<UNK>`.
- Due to high memory and processing requirements, a subset of the data was used for training.

---

## Methodology
1. **Model Architecture**:
   - Used **LSTM** for sequence prediction.
   - Implemented **Word2Vec** for word embeddings.
   - Trained models with different sequence lengths (1, 2, 5, 10).

2. **Training**:
   - Forward and backward word training.
   - Shorter sequence models generated more meaningful text.
   - Longer sequence models tended to repeat frequent words.

3. **Sentence Selection**:
   - Best sentences were selected by measuring the conditional probability of each word and multiplying them.
   - Avoided local maxima by not using a greedy method.

4. **Keyword Implementation**:
   - A user-supplied keyword was used to guide text generation.

