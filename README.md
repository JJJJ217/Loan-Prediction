# Loan Approval Prediction using Machine Learning

## Project Overview

Financial institutions receive thousands of loan applications each year and must assess the risk associated with each applicant before approving a loan. This project develops a machine learning model to predict whether a loan application will be approved based on an applicant's demographic information, household income, and credit history.

The project demonstrates an end-to-end machine learning workflow, including data cleaning, exploratory data analysis, feature engineering, model development, and model evaluation.

---

## Business Problem

The objective of this project is to predict whether an applicant's loan application will be approved based on their:

* Demographic characteristics
* Financial information
* Credit history

Accurate loan approval predictions can help financial institutions improve decision-making, reduce risk, and streamline the loan assessment process.

---

## Dataset

The dataset contains historical loan application records with information relating to applicants and their loan outcomes. **Note:** The dataset is not included in this repository because it is ignored by Git and must be downloaded directly from Kaggle.

### Dataset Source

[Loan Prediction Problem Dataset on Kaggle](https://www.kaggle.com/datasets/altruistdelhite04/loan-prediction-problem-dataset)

### Features

| Variable | Description |
| :--- | :--- |
| Gender | Applicant gender |
| Married | Marital status |
| Dependents | Number of dependents |
| Education | Education level |
| Self_Employed | Employment status |
| ApplicantIncome | Applicant monthly income |
| CoapplicantIncome | Co-applicant monthly income |
| LoanAmount | Requested loan amount |
| Loan_Amount_Term | Loan repayment period |
| Credit_History | Credit history record |
| Property_Area | Property location |
| Loan_Status | Loan approval status (Target Variable) |

### Download Instructions

* Create a Kaggle account and generate an API token from your account settings.
* To authenticate, set the token as an environment variable:
  ```bash
  export KAGGLE_API_TOKEN=<your_generated_token>
  ```
* Alternatively, save it to an `access_token` file (macOS/Linux):
  ```bash
  mkdir -p ~/.kaggle && echo <your_generated_token> > ~/.kaggle/access_token && chmod 600 ~/.kaggle/access_token
  ```
* Once authenticated, you can download the dataset locally into your `dataset/` directory.

---

## Project Scope

This project includes:

* Data cleaning and preprocessing
* Missing value treatment
* Exploratory Data Analysis (EDA)
* Feature engineering
* Feature transformation
* Classification model development
* Model performance evaluation
* Business insight generation

---

## Data Cleaning

The following preprocessing steps were performed:

* Handled missing values using mode and median imputation.
* Corrected data types where necessary.
* Encoded categorical variables using Label Encoding.
* Checked for duplicate records.
* Prepared data for machine learning modelling.

---

## Exploratory Data Analysis

EDA revealed several important patterns:

* Loan approvals significantly outnumber loan rejections.
* Credit history has the strongest relationship with loan approval.
* Married applicants have higher approval rates than unmarried applicants.
* Applicant income is highly skewed due to extreme outliers.
* Household income provides stronger predictive value than individual income.

---

## Feature Engineering

To improve model performance, additional features were created:

### Total Household Income

Combining applicant and co-applicant income:
`Total Income = ApplicantIncome + CoapplicantIncome`

### Log Transformation

A logarithmic transformation was applied to Total Income to:

* Reduce skewness
* Minimise the impact of extreme outliers
* Improve model learning

---

## Machine Learning Models

The following classification algorithms were evaluated:

### Logistic Regression

* Simple and interpretable
* Effective for binary classification problems

### Random Forest Classifier

* Ensemble learning algorithm
* Capable of modelling non-linear relationships

**Dataset split:**

* Training Set: 80%
* Testing Set: 20%

---

## Model Performance

| Model | Accuracy |
| :--- | :--- |
| Logistic Regression | 78.86% |
| Random Forest | 76.42% |

### Best Performing Model

Logistic Regression achieved the highest overall accuracy and was selected as the final model.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Project Structure

```text
LOAN-PREDICTION/
│
├── .venv/
│   ├── bin/
│   ├── include/
│   ├── lib/
│   ├── share/
│   ├── .gitignore
│   └── pyvenv.cfg
│
├── dataset/
│   ├── test.csv
│   └── train.csv
│
├── .gitignore
├── analysis.ipynb
├── business insights
└── README.md
```