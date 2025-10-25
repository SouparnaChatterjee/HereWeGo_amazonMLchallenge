# Smart Product Pricing Challenge 2025

## Overview
This project predicts optimal e-commerce product prices using product descriptions only. It was developed as part of the Smart Product Pricing Challenge 2025 to enhance pricing accuracy, customer trust, and profitability through data-driven machine learning.

## Methodology
The pipeline includes text preprocessing, regex-based numeric extraction (e.g., “Pack of 2”), and TF-IDF vectorization (unigrams + bigrams, 2200 dimensions). Additional numeric features include pack size, word count, and character count. Prices were log-transformed (`log1p`) to reduce skewness.

## Modeling
An ensemble of CatBoost, LightGBM, and XGBoost regressors was trained with a learning rate of 0.045 and 2500 boosting rounds. Predictions were averaged in the log domain and converted back to the original scale. Outputs below 0.01 were clipped.

## Evaluation
The model achieved 18–22% SMAPE on validation data using an 80/20 split. LightGBM captured broad trends, CatBoost handled categorical cues, and XGBoost managed outliers, with the ensemble outperforming any single model.

## Future Work
- Integrate transformer-based embeddings (e.g., DistilBERT, Sentence-BERT)
- Incorporate metadata (brand, category)
- Apply cross-validation-based ensembling for improved stability

## Summary 
A text-driven ML model predicted optimal e-commerce prices using TF-IDF features, regex-based numeric extraction, and an ensemble of CatBoost, LightGBM, and XGBoost. Trained on log-transformed prices, it achieved 18–22% SMAPE. Future work includes transformer embeddings and metadata.

---
© 2025 Smart Product Pricing Team

