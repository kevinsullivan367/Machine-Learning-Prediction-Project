# Smoking Status Prediction Project - All analysis conducted in R

---

## Problem Statement  
Smoking causes over 8 million deaths annually worldwide, including 1.3 million from second-hand smoke. Predicting smoking status from biological signals can aid public health efforts by identifying smokers early and tailoring interventions. This project evaluates machine learning methods to classify smoking status using bio-signals data.

---

## Dataset Overview  
- Source: Kaggle competition **“Quitting Smoking - BGU2025”**  
- Observations: 159,256  
- Features: 24 bio-signal variables (e.g., cholesterol, blood pressure, dental caries)  
- Outcome: Binary indicator for smoking status (smoker vs non-smoker)  
- Data Quality: No missing values or outliers detected  

---

## Feature Engineering  
- Created BMI by combining height and weight  
- Reduced feature set from 24 to 9 based on:  
  - Statistical significance in logistic regression  
  - Public health literature identifying key predictors  
- Final 9 features: age, BMI, systolic & diastolic blood pressure, HDL, LDL, triglycerides, dental caries  

---

## Methods  
- Classification algorithms evaluated:  
  - Logistic Regression (base R)  
  - k-Nearest Neighbors (k = 1 to 100)  
  - Linear Discriminant Analysis (LDA)  
  - Quadratic Discriminant Analysis (QDA)  
  - Naive Bayes  
  - Stepwise Selection (forward, backward)  
  - Lasso and Ridge Regression (model shrinkage)  
- Cross-validation: 5-fold and 10-fold  
- Models trained and validated on both full and reduced feature sets  
- Performance metric: Misclassification error and ROC AUC (Kaggle leaderboard score)  

---

## Results  
- Total models run: 49,671  
- Misclassification error range: 20.4% – 38.5%  
- Best performing model: Logistic regression with 5-fold CV using 5 features (age, HDL, LDL, triglycerides, dental caries)  
  - Misclassification error: 20.4%  
  - Kaggle ROC AUC: 0.75 (ranked 4th)  
- Forward stepwise selection (19 features) had highest Kaggle score but higher error and complexity  

---

## Discussion  
- Logistic regression with a reduced feature set offers a balance of accuracy and simplicity  
- Bio-signals alone are limited in predicting smoking due to behavioral and socioeconomic factors not captured in the data  
- Models with fewer predictors are preferred for ease of clinical implementation  
