# Loan Default Prediction

This project focuses on creating machine learning models to predict loan default risks, enabling financial institutions to mitigate potential losses. The primary objective is to classify borrowers into categories based on their likelihood of defaulting on loans.

## Project Objective

- Predict loan default risk using borrower and loan characteristics.
- Develop models to accurately classify borrowers into 'likely to default' and 'unlikely to default' categories.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Data Exploration](#data-exploration)
- [Data Preprocessing](#data-preprocessing)
- [Data Mining and Modeling](#data-mining-and-modeling)
- [Model Evaluation](#model-evaluation)
- [Conclusion and Recommendations](#conclusion-and-recommendations)
- [Setup and Execution](#setup-and-execution)
- [Technologies Used](#technologies-used)

## Introduction

Loan default prediction is essential for risk management in financial institutions, helping to reduce economic losses by identifying potential defaulters in advance.

## Dataset

The dataset utilized is the Lending Club dataset from Kaggle, containing:

- 396,030 entries
- 27 features (numerical and categorical)

Key variables include:
- Loan Amount (`loan_amnt`)
- Annual Income (`annual_inc`)
- Debt-to-Income Ratio (`dti`)
- Mortgage Accounts (`mort_acc`)
- Home Ownership (`home_ownership`)
- Loan Purpose (`purpose`)
- Loan Application Type (`application_type`)

## Data Exploration

- **Descriptive Statistics:** Analyzed central tendencies, dispersion, and distribution.
- **Visualizations:** Generated histograms, box plots, scatter plots, KDE plots, and count plots to identify patterns, correlations, and distributions of key variables.

## Data Preprocessing

- Handled missing data using mode and strategic imputation.
- Transformed data types for compatibility (numerical, categorical, datetime).
- Removed irrelevant columns to enhance model focus.
- Addressed class imbalance using techniques like SMOTE, Sampling, and Class Weights.
- Removed outliers from influential variables (`dti`, `annual_inc`, `open_acc`, etc.)

## Data Mining and Modeling

Developed multiple machine learning models to classify loan defaults:

### Models Implemented:

- **Naïve Bayes Classifier:** Simplicity and quick implementation, ideal for establishing a baseline.
- **Random Forest:** Ensemble model known for high accuracy and robustness against overfitting.
- **XGBoost:** Advanced gradient boosting model recognized for superior predictive performance.
- **Logistic Regression:** Provides clear interpretability and baseline comparison.

## Model Evaluation

### Metrics used:
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

### Results Summary:

| Model              | Accuracy (Test) | F1-Score (Charged Off) | Best Technique      |
|--------------------|-----------------|------------------------|---------------------|
| Naïve Bayes        | 67.35%          | 40%                    | SMOTE               |
| Logistic Regression| 72.48%          | 35%                    | PCA with SMOTE      |
| Random Forest      | 68%             | 42%                    | SMOTE               |
| XGBoost            | 80.69%          | 17%                    | SMOTE               |

### Best Model Insights:
- **XGBoost with SMOTE:** Best at predicting "Fully Paid" loans (high recall and accuracy).
- **Logistic Regression with Class Weights:** Best for predicting "Charged Off" loans (high recall).

## Conclusion and Recommendations

- **Fully Paid Loans:** Recommend using XGBoost with SMOTE due to its high accuracy and recall.
- **Charged Off Loans:** Logistic Regression with Class Weights recommended for critical financial decisions, emphasizing recall to prevent losses.

## Setup and Execution

### Requirements

- Python 3.x
- Pandas, NumPy, scikit-learn, Matplotlib, XGBoost, imbalanced-learn

### Execution

```bash
git clone <repository-url>
jupyter notebook
```

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- scikit-learn
- XGBoost
- imbalanced-learn (SMOTE)

