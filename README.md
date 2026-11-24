# Restaurant Reviews Sentiment Analysis

## Project Overview

This project applies **Natural Language Processing (NLP)** techniques and Machine Learning to perform sentiment analysis on restaurant reviews.

The goal is to classify customer reviews as positive or negative based on their textual content. The project follows a complete text classification pipeline, including text preprocessing, feature extraction, model training, and performance evaluation.

## Dataset

The project uses the `Restaurant_Reviews.tsv` dataset, containing 1,000 restaurant reviews labeled according to customer sentiment.

- **Input:** Customer reviews (text).
- **Target:** Sentiment classification.
- **Labels:**
  - `0`: Negative review
  - `1`: Positive review

## Technologies & Libraries

- Python
- NumPy
- Pandas
- Matplotlib
- NLTK (Natural Language Toolkit)
- Scikit-learn

## Methodology

The project was developed through the following steps:

### 1. Data Loading

Imported the dataset using Pandas, handling the tab-separated file format (`.tsv`).

### 2. Text Preprocessing

Applied several Natural Language Processing techniques to clean and normalize the reviews:

- Removed non-alphabetic characters.
- Converted all text to lowercase.
- Tokenized sentences into individual words.
- Removed English stopwords, keeping the word "not" to preserve negation and its impact on sentiment.
- Applied stemming using the Porter Stemmer algorithm.

### 3. Feature Extraction

Converted the cleaned text into numerical features using the **Bag of Words (BoW)** model.

The `CountVectorizer` method was configured to retain a maximum of 1,000 features, transforming the text corpus into a numerical matrix suitable for machine learning.

### 4. Train-Test Split

Split the dataset into training and testing sets:

- Training set: 80%
- Testing set: 20%
- Random state: 0

### 5. Model Training

Trained a **Random Forest Classifier** using Scikit-learn, configured with 150 decision trees (`n_estimators=150`).

The model learned patterns from the numerical representation of the reviews to predict their sentiment.

### 6. Model Evaluation

Evaluated the model using a confusion matrix and accuracy score to measure its classification performance on unseen data.

## Results

The model achieved an accuracy of **77.5%** on the test set.

### Confusion Matrix

| | Predicted Negative | Predicted Positive |
|---|---:|---:|
| Actual Negative | 84 | 13 |
| Actual Positive | 32 | 71 |

### Performance Summary

- **Accuracy:** 77.5%
- **True Negatives:** 84
- **True Positives:** 71
- **False Positives:** 13
- **False Negatives:** 32

The results indicate that the model correctly classified 155 out of 200 reviews in the test set.

## Key Takeaways

This project demonstrates the application of NLP techniques to a real-world text classification problem.

Key concepts explored include:

- Text preprocessing and normalization.
- Stopword removal and stemming.
- Bag of Words feature extraction.
- Supervised machine learning.
- Random Forest classification.
- Model evaluation using a confusion matrix and accuracy.

## Future Improvements

Potential improvements to explore:

- Experiment with TF-IDF for feature extraction.
- Compare Random Forest with other classification algorithms, such as Naive Bayes, Logistic Regression, and Support Vector Machines.
- Perform hyperparameter tuning.
- Evaluate additional metrics, including precision, recall, and F1-score.
- Explore more advanced NLP techniques and word embeddings.
