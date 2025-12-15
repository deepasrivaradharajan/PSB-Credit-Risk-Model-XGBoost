# Ultimate Explainable AI (XAI) for Credit Risk Forecasting
PSB / Government Bank Analytics Portfolio Project

## EXECUTIVE SUMMARY

This project presents a robust, end-to-end Machine Learning solution designed for the Indian Public Sector Banking (PSB) environment. It utilizes the high-performance **XGBoost Classifier** to predict loan default risk and addresses the mandatory requirement for **Model Risk Management (MRM)** compliance, as laid out by the Reserve Bank of India (RBI).

The model is built on synthetic, high-dimensional data reflective of real-world banking factors (Aadhaar linkage, tenure, sourcing channel) and is evaluated using metrics critical to bank risk officers: **Gini Coefficient** (discriminatory power) and **Population Stability Index (PSI)** (model monitoring).

## KEY RESULTS AND BUSINESS VALUE

The table below summarizes the model's key metrics.

| Metric | Business Focus | Model Result (Dynamic) | Relevance to Banking |
| :--- | :--- | :--- | :--- |
| Gini Coefficient | Model Discriminatory Power | ~0.65 - 0.75 | Quantifies the model's ability to separate good loans from bad loans. High Gini means better risk selection. |
| Default Recall | Loss Prevention | ~65 percent - 75 percent | Percentage of actual defaulters correctly flagged. Crucial for minimizing Non-Performing Assets (NPAs). |
| PSI Score | Model Stability Monitoring | Less than 0.10 | Assesses if the feature distribution has shifted between training and testing data, a critical step in MRM. |
| Technology | Industry Standard | XGBoost, Python | Demonstrates proficiency in state-of-the-art predictive modeling. |

## TECHNICAL IMPLEMENTATION AND DATA PIPELINE

This project follows a professional MLOps lifecycle from data acquisition to model explainability.

### 1. Data Acquisition and Cleaning

- Source: Synthetic data generation mimicking a bank's core system extract (ultimate_psb_risk_data.csv).
- File I/O: Demonstrates competence in loading large data files using pandas.read_csv().
- Imputation: Handled missing values (NaN) in the Asset_Value_Lakhs feature (simulating unsecured loans) using intelligent imputation techniques, showing robustness to real-world data quality issues.
- Feature Engineering: Created high-impact features like Debt_to_Income_Ratio and LTV_Ratio.

### 2. Modeling (XGBoost)

The model uses XGBoost, a powerful, gradient-boosting framework known for its superior accuracy in structured data classification problems. Hyperparameters were tuned, and scale_pos_weight was used to address class imbalance (since defaults are rare).

## REGULATORY COMPLIANCE AND EXPLAINABILITY (XAI)

For PSB/Govt. Bank roles, this is the most important section. Banks cannot deploy "Black-Box" models.

### A. Feature Importance Plot

The model's Feature Importance is extracted and visualized to provide eXplainable AI (XAI). This is necessary for a human credit manager to understand why a particular loan was approved or rejected, satisfying RBI transparency guidelines.

Top Risk Drivers: (See XGBoost_Feature_Importance_PSB.png)

1. Credit_Score
2. Debt_to_Income_Ratio
3. Loan_Amount_Lakhs
4. Aadhaar_Verified

### B. Model Monitoring Metrics

The inclusion of Gini and PSI metrics demonstrates an understanding of the ongoing monitoring requirements for models post-deployment.

- PSI Score: A low PSI confirms that the model is still reliable because the underlying distribution of customer data (e.g., Credit Score) has not significantly changed since training.

## REPOSITORY STRUCTURE

| File Name | Description | Purpose |
| :--- | :--- | :--- |
| Ultimate_PSB_Risk_Model.ipynb | The complete Python source code and execution log. | Core Project File |
| ultimate_psb_risk_data.csv | The synthetic, high-dimensional raw data used for training. | Data Transparency |
| XGBoost_Feature_Importance_PSB.png | Visualization of the top risk drivers (XAI). | Regulatory Audit/Explainability |
| Confusion_Matrix_PSB.png | Heatmap showing True/False Positives/Negatives. | Loss Assessment and Model Evaluation |
| README.md | This file: Project summary, results, and technical overview. | Recruiter Review |

## SETUP AND EXECUTION

### Requirements

- Python 3.8 plus
- pandas, numpy, matplotlib, scikit-learn, xgboost

### Local Setup (Recommended)

1. Clone the Repository (using your GitHub username):
   bash
    git clone [https://github.com/deepasrivaradharajan/PSB-Credit-Risk-Model-XGBoost.git](https://github.com/deepasrivaradharajan/PSB-Credit-Risk-Model-XGBoost.git)
    cd PSB-Credit-Risk-Model-XGBoost
    

2. Install Libraries:
   bash
    pip install pandas numpy matplotlib scikit-learn xgboost
    

3. Run the Project: Open the Jupyter Notebook/Colab file and run all cells sequentially.
    bash
    jupyter notebook Ultimate_PSB_Risk_Model.ipynb
    
