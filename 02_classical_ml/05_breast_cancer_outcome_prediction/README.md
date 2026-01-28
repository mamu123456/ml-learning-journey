# Breast Cancer Outcome Prediction

## Project Context
This project focuses on predicting breast cancer survival outcomes using patient and tumor characteristics available at the time of diagnosis.

The goal of this work was to practice building and evaluating classification models in a healthcare-related context.

This is a learning project and is not intended for clinical use. All decisions related to the healthcare domain were informed by external research and consultation with publicly available medical resources, as I do not have formal clinical training.

---

## Dataset
- Source: SEER Breast Cancer Dataset (via Zenodo)
- Link: https://zenodo.org/record/5120960

The dataset contains demographic and clinical features such as age, tumor size, lymph node involvement, cancer stage, and tumor grade.

---

## Problem Statement
Given patient and tumor features available at diagnosis, predict whether a patient will survive or not.

This is a binary classification problem where correctly identifying high-risk patients is particularly important.

---

## Data Preparation and Preprocessing

### Avoiding Data Leakage
The dataset includes a feature representing **Survival Months**.  
Since this information would not be available at the time of diagnosis, including it would effectively give the model access to the outcome it is supposed to predict.

To prevent data leakage, this feature was dropped before model training.

---

### Ordinal Feature Encoding
Several categorical features have an inherent order (e.g., cancer stage, tumor grade).  
Instead of one-hot encoding, ordinal mappings were applied to preserve these relationships.

Examples include:
- Tumor stage (T1 < T2 < T3 < T4)
- Lymph node stage (N1 < N2 < N3)
- Cancer stage progression (IIA → IIIC)
- Tumor grade (Well differentiated → Undifferentiated)
- Metastasis stage (Regional < Distant)

This approach was chosen to better reflect clinical progression in the model input.

---

## Models Evaluated
- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)

Models were evaluated using multiple metrics to account for class imbalance and clinical relevance.

---

## Results Summary

Across all models:
- Accuracy was relatively high
- Recall for the minority class (deceased patients) was very low
- Specificity for the majority class (alive patients) was very high
- Logistic Regression achieved the highest ROC AUC and lowest log loss

---

## Limitations
- Strong class imbalance limited the models’ ability to identify high-risk patients
- No resampling or class-weighted techniques were applied
- Feature engineering was limited to ordinal encoding

---

## What I Would Improve Next
This project was limited by my knowledge and exposure at the time (October 2025). With the knowledge I have now, I would improve on this by:
- Exploring techniques to address class imbalance (e.g., class weighting or resampling)
- Focusing on improving recall for the minority class
- Experiment with changing the decision threshold so the model prioritizes identifying high-risk patients rather than overall accuracy.
- Adding model interpretability analysis to better understand predictions

---

## Status
Learning project — feedback and critique welcome
