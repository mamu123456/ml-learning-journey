# Loan Default Prediction

## Project Context
This project was completed as a collaborative learning exercise using a Kaggle Playground Series dataset. 

The primary goal was to practice model comparison and hyperparameter optimization.

The project focused on improving model performance through structured experimentation and tuning.

---

## Collaboration
This was a group project completed in collaboration with: [Gideon Pam](https://github.com/Gideonpam)

Collaboration helped expose me to alternative modeling choices and evaluation perspectives.

We discussed modeling strategies, shared experimentation ideas, and reviewed results together.  

---

## Dataset
- Source: Kaggle Playground Series
- Dataset: Loan Default Prediction
- Link: https://www.kaggle.com/competitions/playground-series-s5e11/overview

The dataset is publicly available and commonly used for educational and benchmarking purposes.

---

## Problem Statement
The task is a binary classification problem:  
predict whether a loan will default based on applicant and loan-related features.

---

## Approach
- Exploratory data analysis and preprocessing
- Training multiple baseline classification models
- Evaluation using accuracy, precision, recall, F1 score, and ROC AUC
- Hyperparameter optimization using **Optuna**
- Comparison of baseline vs optimized models

---

## Models Evaluated
- Logistic Regression
- Random Forest
- Gradient Boosting
- XGBoost

Two models were further optimized using Optuna:
- Random Forest
- Gradient Boosting

---

## Results Summary

| Model | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.88100 | 0.8956 | 0.9626 | 0.9279 | 0.8822 |
| Random Forest | 0.89425 | 0.8902 | 0.9890 | 0.9370 | 0.8802 |
| Gradient Boosting | 0.90000 | 0.8916 | 0.9953 | 0.9406 | 0.8961 |
| XGBoost | 0.89175 | 0.8940 | 0.9802 | 0.9351 | 0.8768 |
| Optimized Gradient Boosting | 0.89700 | 0.8908 | 0.9921 | 0.9387 | 0.8989 |
| Optimized Random Forest | 0.89450 | 0.8903 | 0.9893 | 0.9372 | 0.8843 |

---

## Key Learnings
- Hyperparameter optimization can improve model performance, but gains are often incremental rather than dramatic
- Different evaluation metrics highlight different model strengths (e.g., recall vs ROC AUC)
- Optimizing for one metric does not always improve others
- Feature engineering benefits from domain understanding, and discussing feature ideas with a collaborator helped improve my approach.
- Seeing a different modeling workflow highlighted alternative ways to think about the same problem.
- Hyperparameter optimization improves performance, but feature design and metric selection remain equally important.

---

## Limitations
- Feature engineering was limited
- Class imbalance handling could be explored further
- No deployment or real-world validation was performed
- Results are specific to this dataset and may not generalize

---

## What I Would Improve Next
- Further explore domain-driven feature engineering by testing additional ratios and interactions inspired by financial risk assessment.
- Analyze the impact of engineered features more explicitly to understand which transformations contribute most to model performance.
- Continue comparing model performance before and after hyperparameter optimization to better understand where tuning provides meaningful gains.
- Examine the class distribution of the target variable more closely and assess whether class imbalance influenced model behavior, particularly the high recall scores.
- Experiment with techniques such as class-weighted loss functions or resampling methods to understand their impact on performance.
  
---
 
* Additional feedback and critique welcome
