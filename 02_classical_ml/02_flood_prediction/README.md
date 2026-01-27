# Predicting Probability of Flooding

## Problem Statement
The objective of this project was to frame a regression problem, explore the dataset, and build a leak-free preprocessing and modeling pipeline to predict flooding probability.
Date Submitted: October 13th, 2025

---

## Dataset
The dataset was provided as a CSV for academic purposes.  
The original source is unknown.

---

## Approach
- Exploratory data analysis
- Preprocessing pipeline construction
- Baseline regression modeling
- Model evaluation using MAE, RMSE, and R²

---

## Results
- Linear Regression:
  - MAE = 0.000
  - RMSE = 0.000
  - R² = 1.000
- Random Forest Regressor:
  - MAE = 0.020
  - RMSE = 0.026
  - R² = 0.735

---
---

## Post-Analysis Note on Model Results (Learning Reflection)

When I evaluated the models, I noticed that the Linear Regression model produced perfect results (R² = 1.000 and zero error), which immediately felt unrealistic.

At the time, I did not fully understand why this was happening, so I used AI tools as a learning aid to help interpret the results and understand what could cause such behavior.

Based on that guidance, I learned that this can happen when:
1. The target variable is directly calculated from the input features, meaning the model is not really “predicting” but instead reproducing a fixed relationship already present in the data.
2. There is data leakage, where the target variable (or information derived from it) is indirectly included in the input features, allowing the model to effectively “see” the answer.
3. The same data (or overlapping data) is used for both training and testing, which can result in perfect evaluation scores without true generalization.

To explore this further, I followed suggested steps to compare the mathematical structure of the input features and the target variable. This helped confirm that the target did not contain new information beyond what was already in the features.

This was an important learning moment for me, as it showed that:
- Perfect evaluation metrics can be misleading
- High performance does not always mean a model is useful
- It is important to question results that seem too good to be true

---

## What I Would Improve

I would:
- Use additional visualizations to more meaningfully support reasoning both during exploration and in demonstration or extraction of the final insights
- Add more explanatory code comments and markdown  for each pipeline stage
- Analyze the dataset and feature definitions with a better understanding of data leakage to check whether the target variable (or information derived from it) is unintentionally included in the inputs.
- Rebuild the model after addressing any leakage to see how performance changes under more realistic assumptions.

---

## Feedback Welcome

- Is this the correct way to interpret such perfect results?
- How would an experienced practitioner detect this issue earlier during exploration?
- What additional checks would typically be performed in real-world projects?
