# 🏦 Bank Customer Churn Prediction

Machine learning project to predict **bank customer churn** using customer behavior and profile data, with a focus on **class imbalance**, model optimization, and evaluation using **F1-score** and **ROC-AUC**.

## 📌 Context

Customer retention is a critical challenge in the banking industry. Acquiring new customers can be more expensive than retaining existing ones, making early identification of customers at risk of leaving particularly valuable.

In this project, historical customer data from **Beta Bank** is analyzed to build a machine learning model capable of predicting whether a customer is likely to leave the bank.

The project was developed as part of my Data Science studies and reorganized for portfolio presentation.

## 🎯 Problem

The objective is to build a classification model that predicts customer churn.

The main evaluation requirement is:

- achieve an **F1-score of at least 0.59** on the test dataset.

In addition to F1-score, **ROC-AUC** is evaluated to provide another perspective on the model's ability to distinguish between customers who leave and those who remain.

A key challenge is the **class imbalance** in the target variable, requiring specific techniques to improve the model's ability to identify churned customers.

## 📊 Dataset

The project uses the `Churn.csv` dataset containing customer profile and banking behavior information.

### Features

- `CreditScore` — customer's credit score
- `Geography` — country of residence
- `Gender` — customer gender
- `Age` — customer age
- `Tenure` — number of years associated with the bank
- `Balance` — account balance
- `NumOfProducts` — number of banking products used
- `HasCrCard` — whether the customer has a credit card
- `IsActiveMember` — whether the customer is an active member
- `EstimatedSalary` — estimated salary

### Target

- `Exited` — whether the customer left the bank:
  - `1` — customer churned
  - `0` — customer remained

Columns used only as identifiers, such as `RowNumber`, `CustomerId`, and `Surname`, are excluded from model training.

## 🔎 Approach

The analysis follows a structured machine learning workflow:

1. Data loading and inspection
2. Data cleaning and preprocessing
3. Feature selection
4. Encoding categorical variables
5. Train, validation, and test split
6. Class distribution analysis
7. Baseline model training
8. Evaluation of class imbalance strategies
9. Hyperparameter tuning
10. Model selection using F1-score
11. Final evaluation on the test dataset
12. ROC-AUC comparison

## ⚖️ Class Imbalance

The target variable is imbalanced, with substantially fewer customers leaving the bank than remaining.

A model trained without addressing this imbalance may favor the majority class and perform poorly when identifying customers who actually churn.

To address this problem, different strategies were evaluated, including:

- **class weighting** using `class_weight='balanced'`;
- **upsampling** of the minority class.

The models were compared using validation F1-score to determine which approach provided the strongest performance.

## 🤖 Machine Learning

A **Random Forest Classifier** was used as the main classification algorithm.

Different hyperparameter configurations were evaluated using the validation dataset, including variations in the number of trees and tree depth.

The final model was selected based primarily on **F1-score**, while ROC-AUC was used as an additional evaluation metric.

## 📈 Model Evaluation

Two primary metrics were used:

### F1-score

F1-score balances **precision** and **recall**, making it particularly useful when working with imbalanced classification problems.

The project requirement was:

**F1-score ≥ 0.59**

The final model achieved approximately:

**F1-score: 0.603**

### ROC-AUC

ROC-AUC measures the model's ability to distinguish between the two target classes across different classification thresholds.

The final model achieved approximately:

**ROC-AUC: 0.852**

Together, these metrics provide complementary perspectives on model performance.

## 💡 Key Findings

The analysis highlights several important machine learning considerations:

- customer churn is an imbalanced classification problem;
- ignoring class imbalance limits the model's ability to identify customers who leave;
- class balancing strategies improve classification performance;
- both class weighting and upsampling provide useful approaches for handling imbalance;
- hyperparameter tuning further improves model performance;
- F1-score and ROC-AUC provide complementary information about classification quality.

The final model exceeded the required **0.59 F1-score threshold** on the test dataset.

## 🚀 Business Applications

A churn prediction model can support customer retention strategies by helping a bank:

- identify customers with higher churn risk;
- prioritize retention campaigns;
- target customers with personalized offers;
- allocate customer-service resources more efficiently;
- reduce customer acquisition costs by improving retention;
- support proactive relationship management.

In a production environment, predicted churn probabilities could be integrated into CRM or customer engagement systems to trigger targeted retention actions.

## ⚠️ Limitations

This project focuses on predictive modeling using the available historical dataset.

The analysis does not establish causal relationships between customer characteristics and churn.

Additionally:

- customer behavior may change over time;
- the cost of false positives and false negatives is not explicitly modeled;
- no financial value is assigned to individual customer retention;
- model performance should be monitored if deployed on new customer populations.

Further development could include probability threshold optimization, additional algorithms, feature engineering, and business-oriented cost-sensitive evaluation.

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Random Forest
- Jupyter Notebook

## 📁 Repository Structure

```text
bank-customer-churn-prediction/
│
├── README.md
│
├── data/
│   └── Churn.csv
│
└── notebook/
    └── bank_customer_churn_prediction.ipynb
```

## ▶️ Running the Project

Clone the repository and open the Jupyter Notebook located in the `notebook` directory.

The dataset used by the notebook is stored in the `data` directory.

The analysis requires **Python**, **Pandas**, **NumPy**, **Matplotlib**, and **Scikit-learn**.

---

### Author

**Brunno Almeida**

Data Science | Data Analytics | Python | SQL | Machine Learning
