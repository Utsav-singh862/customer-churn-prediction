# Customer Churn Prediction

A machine learning project that predicts whether a customer will churn using a Logistic Regression classifier.

## Project overview

Customer churn is when a customer stops using a product or subscription. This project explores customer data, prepares categorical features, trains a classification model, and evaluates its predictions.

## Dataset

`customer_churn_dataset.csv` contains 200 rows and 11 columns, including customer demographics, subscription and payment details, support tickets, contract type, and the target column `Churn`.

> Use this dataset only if you have the right to share it publicly. Do not upload real customer data or personally identifiable information.

## Workflow

1. Load and inspect the dataset with pandas.
2. Remove `CustomerID` because it is an identifier rather than a predictive feature.
3. Encode `Gender` and one-hot encode subscription, payment, and contract categories.
4. Split the data into training and test sets using stratification.
5. Train a Logistic Regression classifier.
6. Evaluate with a classification report, confusion matrix, and ROC-AUC.
7. Save the trained model and feature-column list under `model_artifacts/`.

## Requirements

- Python 3.10+ (or a compatible Python version)
- pandas
- scikit-learn
- seaborn
- matplotlib
- Jupyter Notebook

## Run locally

```bash
git clone <your-repository-url>
cd customer-churn-prediction

python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
jupyter notebook
```

Open `churn_prediction.ipynb` and run the cells from top to bottom. Keep the notebook and CSV in the same directory.

## Repository structure

```text
customer-churn-prediction/
├── churn_prediction.ipynb
├── customer_churn_dataset.csv
├── requirements.txt
└── README.md
```

The generated model artifact is intentionally excluded from Git by `.gitignore`; run the final notebook cell to create it locally.

## Important limitation

This is a starter project, not a production churn system. Before using it for business decisions, compare against a baseline and other models, check class balance and data leakage, tune the decision threshold, and validate on data from a later time period. Reported metrics on a small test set can be unstable.
