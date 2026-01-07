# Predicting Clinically Relevant Anxiety Risk among Gamers

## 📘 Course / Project Information

**Project Type:** Data Mining / Machine Learning Semester Project
**Topic:** Predicting Clinically Relevant Anxiety Risk among Gamers
**Platform:** Python, Google Colab

---

## 👥 Group Overview

| ID     | Name              | Email                                                         |
| ------ | ----------------- | ------------------------------------------------------------- |
| 232542 | Abdul Wahab       | [232542@students.au.edu.pk](mailto:232542@students.au.edu.pk) |
| 232585 | Muhammad Shafique | [232585@students.au.edu.pk](mailto:232585@students.au.edu.pk) |
| 232572 | Muhammad Haroon   | [232572@students.au.edu.pk](mailto:232572@students.au.edu.pk) |
| 232563 | Muhammad Bachal   | [232563@students.au.edu.pk](mailto:232563@students.au.edu.pk) |
| 232562 | Talha Bin Omar    | [232562@students.au.edu.pk](mailto:232562@students.au.edu.pk) |

---

## 🧾 Abstract

The rapid growth of digital gaming has raised concerns regarding its potential impact on mental health, particularly anxiety disorders. This project investigates whether clinically relevant anxiety risk among gamers can be predicted using machine learning techniques based on gaming behavior, demographic attributes, and psychological scales. Using a large-scale gaming survey dataset of 13,464 participants, extensive preprocessing, feature engineering, and model evaluation were conducted. The optimized Random Forest model achieved a test ROC-AUC of **0.78** with strong recall, demonstrating the feasibility of ML-based anxiety screening tools for gaming populations.

---

## 📌 Introduction

Online gaming is one of the most widespread forms of entertainment worldwide. While it offers cognitive and social benefits, excessive or maladaptive gaming behavior has been linked with anxiety, depression, and social withdrawal. Early identification of anxiety risk is crucial for timely psychological intervention.

Traditional assessments rely on questionnaires and clinical interviews, which can be time-consuming. Machine learning provides a scalable alternative by learning complex patterns from behavioral and psychological data. This project aims to design a robust classification framework to predict anxiety risk among gamers.

---

## 📊 Dataset Description

The dataset consists of **13,464 observations** and **55 variables**, collected through a large-scale gaming and mental health survey.

### Data Categories

* **Mental Health Measures**

  * GAD-7 (Generalized Anxiety Disorder)
  * Satisfaction With Life Scale (SWL)
  * Social Phobia Inventory (SPIN)

* **Gaming Behavior**

  * Weekly gaming hours
  * Streaming activity
  * Game genre, platform, and playstyle
  * Gaming motivation

* **Demographic Information**

  * Age, gender, education, employment
  * Birthplace and residence (ISO3 codes)

The dataset size and diversity make it suitable for supervised machine learning.

---

## 🎯 Target Variable Definition

The target variable **`anxiety_risk`** was defined using a clinically validated cutoff from the GAD-7 scale:

* `anxiety_risk = 1` → GAD_T ≥ 10 (moderate to severe anxiety)
* `anxiety_risk = 0` → otherwise

This threshold is widely accepted in clinical research, ensuring medical relevance.

---

## 🧹 Data Preprocessing

A rigorous preprocessing pipeline was implemented to ensure data quality and prevent leakage.

### 1️⃣ Column Removal

* Index and timestamp columns
* Administrative and consent-related variables
* Columns with excessive missing values

### 2️⃣ Missing Value Handling

* SPIN items: Median imputation
* GADE: Mode imputation
* Numerical variables: Median imputation
* Advanced imputation: Iterative Imputer (MICE)
* Categorical variables: Mode or "Unknown" category

### 3️⃣ Leakage Prevention

All questionnaire item-level variables contributing to total scores (GAD, SWL, SPIN) were removed after computing totals.

---

## 🛠️ Feature Engineering

To improve performance and interpretability, the following features were engineered:

* Gaming hours: Outlier capping, log transformation, categorical bins
* Streaming activity: Log transformation
* Earnings: Mapped to simplified income categories
* Motivation: Binary indicators (fun, improvement, winning, relaxation)
* Rare games and countries grouped into "Other"
* Standardized playstyle categories

After feature selection, **20 predictive features** were retained.

---

## 🤖 Model Development

A modular machine learning pipeline was implemented:

### Pipeline Components

* **Preprocessing:** StandardScaler + OneHotEncoder
* **Feature Selection:** Mutual Information (SelectKBest)
* **Models Evaluated:**

  * Logistic Regression
  * Calibrated Linear SVM
  * Random Forest Classifier

A **Stratified 5-Fold Cross-Validation** strategy was used to address class imbalance.

---

## 📈 Model Evaluation & Selection

Random Forest was selected due to its balance between performance and interpretability.

* **Best Cross-Validated ROC-AUC:** 0.79
* **Final Selected Model:** Optimized Random Forest

---

## ✅ Final Test Results

Evaluation was performed on a held-out 20% test set.

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.73  |
| Precision | 0.36  |
| Recall    | 0.70  |
| F1-score  | 0.48  |
| ROC-AUC   | 0.78  |

High recall is desirable for mental health screening to minimize missed high-risk individuals.

---

## 🔍 Feature Importance Analysis

Permutation importance revealed the most influential predictors:

1. Social Phobia Score (SPIN_T)
2. Life Satisfaction (SWL_T)
3. Gender
4. Narcissism
5. Gaming Motivation (Fun, Winning)
6. Playstyle and Gaming Intensity

These findings align with established psychological research.

---

## 💬 Discussion

The results demonstrate that anxiety risk among gamers can be effectively predicted using machine learning. Although precision is moderate due to class imbalance, high recall makes the system suitable for early screening and intervention.

---

## 🏁 Conclusion

This project presents a robust ML-based framework for predicting clinically relevant anxiety risk among gamers. The integration of careful preprocessing, feature engineering, and evaluation resulted in a reliable and interpretable predictive system.

---

## 🔮 Future Work

* Incorporation of longitudinal behavioral data
* Use of advanced ensemble models (e.g., Gradient Boosting)
* Fairness and bias analysis across demographics
* Deployment as a real-time mental health screening tool


