# Sentiment140 Analysis

This repository contains a sentiment analysis project using the [Sentiment140 dataset](https://www.kaggle.com/datasets/kazanova/sentiment140). The project applies various vectorization techniques and machine learning models to classify the sentiment of tweets as positive or negative.

## Project Overview
Sentiment analysis helps determine if a text expresses a positive or negative emotion. This project explores the effectiveness of machine learning models in sentiment classification on Twitter data. Using the Sentiment140 dataset, we address challenges such as informal language, diverse writing styles, and complex textual structures.

### Key Highlights
1. Comprehensive text preprocessing pipeline, including handling special characters, URLs, mentions, and negations.
2. Exploration of different vectorization methods: TF-IDF, Count, Hashing, Doc2Vec, FastText, Sentence Transformers, and DistilBERT.
3. Evaluation of various machine learning models: Logistic Regression, Linear SVM, Naive Bayes, Random Forest, and Neural Networks.
4. Final recommendation of the best-performing model and vectorizer combination.

---

## Dataset
The Sentiment140 dataset contains 1.6 million labeled tweets, split equally into positive and negative sentiments:
- **Labels**: 
  - `0`: Negative sentiment
  - `4`: Positive sentiment (converted to `1` for this project)
- **Columns**: 
  - `target`: Sentiment label
  - `text`: The tweet content
  - Other columns (`id`, `date`, `flag`, `user`) were dropped to simplify processing.

**Source**: [Sentiment140 Dataset on Kaggle](https://www.kaggle.com/datasets/kazanova/sentiment140)

---

## Text Preprocessing
A thorough preprocessing pipeline was applied to clean and prepare the text:
1. Removal of HTML artifacts using BeautifulSoup.
2. Handling special encodings and replacing problematic symbols.
3. Elimination of mentions (`@username`) and URLs.
4. Standardizing case by converting text to lowercase.
5. Addressing negations (e.g., "isn't" → "is not").
6. Tokenization of text into individual words.
7. Stemming using the Porter Stemmer.

*Stopword removal and lemmatization were intentionally excluded to preserve critical sentiment-carrying words.*

---

## Data Visualization
- Word clouds were generated to identify common themes in negative and positive tweets.
- Sentiment distributions and most frequent words (with and without stopwords) were analyzed.

---

## Model Testing with Vectorizers
The following vectorizers were tested:
- **TF-IDF (trigram)**: Best-performing vectorizer.
- **Count Vectorizer**: Performed similarly to TF-IDF but slightly lower.
- **Hashing Vectorizer**: Effective but incompatible with Naive Bayes due to negative values.
- **Doc2Vec**: Neural Networks outperformed traditional models.
- **FastText**: Neural Networks achieved the highest accuracy.
- **Sentence Transformers**: Computationally expensive but yielded good results with a sample dataset.
- **DistilBERT**: Similar performance to Sentence Transformers.

### Best Model
- **Vectorizer**: TF-IDF (trigram)
- **Model**: Logistic Regression
- **Accuracy**: 82.30%
- **Metrics**: 
  - Precision: 0.83 (negative), 0.82 (positive)
  - Balanced recall and F1-scores

---

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/sentiment140-analysis.git
   cd sentiment140-analysis

