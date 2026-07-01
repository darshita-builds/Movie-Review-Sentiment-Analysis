##Movie Review Sentiment Analysis (MRSA)

A sentiment classifier that predicts whether an IMDB movie review is positive or negative, built with classic NLP preprocessing and Naive Bayes models.

Overview

This project uses the IMDB dataset of 50,000 movie reviews (balanced 25k positive / 25k negative) to train and compare three Naive Bayes classifiers for binary sentiment classification.

*Pipeline
-Data Loading — Reads IMDB.csv containing review and sentiment columns
-Label Encoding — Maps positive → 1, negative → 0

*Text Cleaning
Removes HTML tags (e.g. <br />)
Strips special characters/punctuation
Converts text to lowercase


*Text Normalization
Removes English stopwords (NLTK)
Applies Snowball stemming


*Feature Extraction — Bag-of-Words representation via CountVectorizer (top 2,000 features)
*Train/Test Split — 80% train, 20% test (random_state=9)
*Model Training — Trains three Naive Bayes variants:

Gaussian Naive Bayes
Multinomial Naive Bayes
Bernoulli Naive Bayes



Model Persistence — Saves Multinomial and Bernoulli models as .pkl files via joblib
Evaluation — Compares accuracy across all three models


Results

ModelAccuracyGaussian Naive Bayes74%Multinomial Naive Bayes84%Bernoulli Naive Bayes85%

Bernoulli Naive Bayes performed best, likely because the Bag-of-Words features here behave as binary presence/absence indicators, which fits the Bernoulli distribution assumption well.

