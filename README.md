# Loan Prediction Project

[![Python](https://img.shields.io/badge/python-3.12%2B-blue)](https://www.python.org/downloads/)

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature Engineering](#feature-engineering)
- [Model Development](#model-development)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project implements a machine learning pipeline for predicting loan approvals. It uses various techniques in data preprocessing, exploratory data analysis, feature engineering, and machine learning modeling to achieve high predictive accuracy.

## Dataset

The project uses two datasets:

- `loan_train.csv`: Training dataset with 491 entries and 13 features
- `loan_test.csv`: Test dataset with 123 entries and 12 features (excluding the target variable)

Key features include:

- Loan_ID
- Gender
- Married
- Dependents
- Education
- Self_Employed
- ApplicantIncome
- CoapplicantIncome
- LoanAmount
- Loan_Amount_Term
- Credit_History
- Property_Area
- Loan_Status (target variable)

## Data Preprocessing

1. Handling missing values:

   - Mode imputation for categorical variables (Gender, Married, Dependents, Self_Employed, Credit_History)
   - Median imputation for numerical variables (LoanAmount)
   - Mode imputation for Loan_Amount_Term
2. Outlier treatment:

   - Log transformation applied to LoanAmount to handle right skewness
3. Encoding categorical variables:

   - One-hot encoding used for all categorical variables

## Exploratory Data Analysis

1. Univariate analysis:

   - Distribution of loan approval status
   - Distribution of categorical variables (Gender, Married, Dependents, Education, Self_Employed, Credit_History, Property_Area)
   - Distribution of numerical variables (ApplicantIncome, CoapplicantIncome, LoanAmount)
2. Bivariate analysis:

   - Relationship between categorical variables and loan approval status
   - Relationship between numerical variables and loan approval status
3. Correlation analysis:

   - Heatmap of correlation between numerical variables

## Feature Engineering

Based on domain knowledge and insights from EDA, we created the following new features:

1. Total_Income: Combination of ApplicantIncome and CoapplicantIncome
3. Total_Income_log: Log transformation of Total_Income
4. EMI: LoanAmount divided by Loan_Amount_Term
5. Balance Income: Total_Income minus (EMI * 1000)

## Model Development

Four models were implemented and evaluated:

1. Logistic Regression
2. Decision Tree
3. Random Forest (Pending)
4. XGBoost (Pending)

Each model was evaluated using 5-fold stratified cross-validation to ensure robust performance estimation.

## Results

Here's a summary of the model performances:

| Model               | Mean Validation Accuracy | Mean Validation F1 Score | AUC    |
| ------------------- | ------------------------ | ------------------------ | ------ |
| Logistic Regression | 0.7881                   | 0.8622                   | 0.8176 |
| Decision Tree       | 0.7168                   | 0.8027                   | 0.7500 |
| Random Forest       | Not implemented          | Not implemented          | N/A    |
| XGBoost             | Not implemented          | Not implemented          | N/A    |

Note: The Random Forest and XGBoost models were mentioned in the project plan but not implemented in the provided notebook.

## Installation

```bash
git clone https://github.com/riziuzi/loan-prediction.git
cd loan-prediction
pip install -r requirements.txt
```

## Contributing

![ImGonnaNeedYourHelpEricCartmanGIF](https://github.com/user-attachments/assets/7bcf9135-0b66-48d7-8368-f373d014f1f7)


Contributions to this project are welcome. Please fork the repository and submit a pull request with your proposed changes.


---

Created by **[**riziuzi**](**https://github.com/riziuzi**)**
