# Sentiment Analysis on Airline Tweets

## Overview

This project implements a sentiment analysis model to classify tweets about major U.S. airlines as positive, neutral, or negative. The dataset, sourced from Kaggle, includes tweets scraped from February 2015, with contributors categorizing sentiments and negative reasons.

## Table of Contents

- [Features]
- [Usage]
- [Models]
- [Performance Evaluation]
- [Deployment Pipeline]
- [Usage Example]
- [Future Scope]
- [Disclaimer]

## Features

- **Data Exploration:** Utilizes pandas, seaborn, and matplotlib for insightful visualizations.
- **Text Vectorization:** Implements TF-IDF vectorization to convert textual data into numerical features.
- **Model Comparisons:** Compares the performance of Naive Bayes, Logistic Regression, and Linear Support Vector Classification (LinearSVC) models.
- **Performance Evaluation:** Evaluates models using classification reports and confusion matrices.

## Usage

1. Explore data with visualizations.
2. Preprocess and vectorize text data using TF-IDF.
3. Compare models: Naive Bayes, Logistic Regression, and LinearSVC.
4. Evaluate model performance with classification reports and confusion matrices.
5. Deploy a pipeline for predicting sentiments on new tweets.

## Deployment Pipeline

Constructs a pipeline using TfidfVectorizer and LinearSVC for streamlined deployment. Allows for predicting sentiments on new tweets directly through the pipeline.

## Usage Example

```python
from sklearn.pipeline import Pipeline

# Construct the pipeline
pipe = Pipeline([('tfidf', TfidfVectorizer()), ('svc', LinearSVC())])
pipe.fit(df['text'], df['airline_sentiment'])

# Predict sentiment on new tweets
new_tweet = ['good flight']
pipe.predict(new_tweet)

new_tweet = ['bad flight']
pipe.predict(new_tweet)

new_tweet = ['ok flight']
pipe.predict(new_tweet)
