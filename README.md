# IBM Telco Customer Churn Prediction

An end-to-end supervised learning project that explores customer churn and compares baseline and tuned logistic regression and decision tree classifiers. The notebook includes exploratory analysis, leakage-aware preprocessing, stratified train/test splitting, cross-validated hyperparameter search, and evaluation with precision, recall, F1, ROC-AUC, and confusion matrices.

## Dataset

The notebook expects `Telco_customer_churn.xlsx` in the project root, with a sheet named `Telco_Churn`. The dataset is not included in this repository. Obtain it from the [IBM Telco Customer Churn dataset on Kaggle](https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset) and check its terms before redistribution.

## Run the notebook

1. Create and activate a Python environment.
2. Install dependencies: `pip install -r requirements.txt`.
3. Place the workbook at `Assignment 1 Dataset.xlsx`.
4. Open and run `IBM_Telco_Customer_Churn.ipynb` from top to bottom.

The split and model initialization use `random_state=42`. Scores are computed by the notebook when run with the dataset; no results are asserted here because the data file is not bundled.

## Project notes

The target is `Churn Value`. The notebook excludes `Churn Label`, `Churn Score`, and `Churn Reason` as leakage risks, along with identifiers and location fields. It fits imputation, scaling, and one-hot encoding within scikit-learn pipelines.

Before deployment, evaluate on later time periods, select a threshold based on retention costs, assess subgroup performance, and monitor drift.
