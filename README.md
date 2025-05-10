# 🎓 Student Final Grade Prediction using Machine Learning

This project aims to predict the **final grade (G3)** of students in secondary school using a machine learning approach. The dataset is sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/), containing various **demographic, academic, social, and lifestyle features** of students. The goal is to help educators and administrators identify students at risk and provide timely academic support.

---

## 📌 Dataset Overview

- **Source**: [Kaggle](https://www.kaggle.com/datasets/tejas14/student-final-grade-prediction-multi-lin-reg/data)
- **Subjects**: Portuguese secondary school students (Mathematics)
- **Target**: Final Grade (G3)
- **Features**: 32 input attributes including:
  - **Demographic**: age, gender, school, address
  - **Parental**: education, job, status
  - **Social**: going out, romantic relationships, free time
  - **Academic**: study time, failures, G1, G2
  - **Other**: absences, health, internet access

> **Note**: G1 and G2 are highly correlated with G3, as they represent grades from earlier terms in the academic year.

---

## 🔍 Exploratory Data Analysis

### ✅ Categorical Features
- Visualized using **pie charts** for class distribution.
- Converted codes like `U`/`R` to `urban`/`rural`, `GP`/`MS` to full school names.
- Extracted insights on family background, internet access, and aspirations for higher education.

### ✅ Numerical Features
- Boxplots used to identify **outliers** in features like `absences`, `G1`, `G2`, etc.
- Correlation matrix helped identify the **most influential predictors** for G3.

---

## ⚙️ Model Training & Evaluation

Six regression models were trained and evaluated on the same dataset:

| Model              | RMSE | MAE  | R² Score |
|-------------------|------|------|----------|
| Linear Regression | 1.83 | 1.30 | 0.838    |
| Ridge Regression  | 1.82 | 1.29 | 0.839    |
| **Lasso Regression** | **1.64** | **1.12** | **0.870** |
| Random Forest     | 1.85 | 1.06 | 0.833    |
| Gradient Boosting | 1.80 | 1.05 | 0.843    |
| XGBRegressor      | 1.80 | 3.47 | 0.830    |

> 🔥 **Lasso Regression** gave the best overall performance with the highest R² and lowest MAE.

---

## 🚀 Model Deployment

The best-performing model (Lasso) was deployed using two platforms:

### ✅ Gradio (Local or Web Interface)

A simple user-friendly form lets you input student details and see the predicted final grade.
