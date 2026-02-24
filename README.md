# Project_Fraud-Detection
Project Overview
This project demonstrates a robust pipeline for identifying fraudulent transactions. The primary challenge was the extreme class imbalance—where legitimate transactions vastly outnumber fraudulent ones. By combining Log Transformation to handle high-variance features and Cost-Sensitive Learning (Weighting) within XGBoost, the model achieved high-fidelity detection without overfitting to noise.

P.S. This data is simulated for Data Science class practicing.

### 1. Statistical Insights & Data Exploration
Before modeling, a thorough comparison of means revealed distinctive "Behavioral Signatures" for fraud.

Based on Mean & S.D Comparison , There are features with strong differance. 

  - transaction_hour
  - foreign_transaction & location_mismatch
  - velocity_last_24h
  - device_trust_score

### 2. Handling Skewness
Since some columns have a high skewness (amount, velocity_last_24h). Transformed Skewed data  to normal distribution by Log Transformation ($np.log1p$) was helpful, It will support XGboost to digest class pattern accurately.

### 3. Encoding
For a quanlitative column like merchant_category we have to convert to dummy variable for calculating.

### 4. Modeling & Imbalance Strategy
The project utilized XGBoost as the primary classifier, specifically tuned for imbalanced data:

Scale Pos Weight: A weight ratio was calculated (Negative Samples / Positive Samples) to penalize the model more heavily for misclassifying the minority (Fraud) class.

Optimization: The model was optimized for AUPRC (Area Under the Precision-Recall Curve) to prioritize fraud detection over simple accuracy.

### 5.Performance Results

  
  
