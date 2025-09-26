# Fraud-Analysis-EDA-XGboost
📝 Problem Definition

Fraudulent financial transactions pose a significant risk to financial institutions, leading to monetary losses, regulatory issues, and erosion of customer trust. Rule-based systems, though widely used, often fail to detect novel fraud patterns and may generate excessive false positives.

This project develops a machine learning–based fraud detection model on a dataset of 6.3 million transactions to enhance fraud detection accuracy while minimizing false alarms.

🎯 Business Objective

The primary business objective is to:

Identify fraudulent transactions with high accuracy in real time.

Reduce financial losses by minimizing undetected fraud cases.

Control false positives to ensure a smooth customer experience.

Support fraud investigation teams with prioritized alerts.

Strengthen security and compliance while maintaining customer trust.

📊 Dataset Description

The dataset contains records of financial transactions with the following attributes:

step: Time unit in hours (1 step = 1 hour, total ≈ 30 days).

type: Type of transaction (CASH-IN, CASH-OUT, TRANSFER, PAYMENT, etc.).

amount: Transaction amount.

nameOrig: Identifier of the origin account.

oldbalanceOrg / newbalanceOrig: Account balance before and after the transaction (origin).

nameDest: Identifier of the destination account.

oldbalanceDest / newbalanceDest: Account balance before and after the transaction (destination).

isFraud: Indicates if the transaction is fraudulent (1 = fraud, 0 = genuine).

isFlaggedFraud: Transactions flagged by the existing detection system.

🔍 Exploratory Data Analysis (EDA)

The following key questions were explored during analysis:

Which transaction types are most vulnerable to fraud?

How does fraud evolve over time (daily/ hourly trends)?

Do fraudulent transactions exhibit unique amount or balance patterns?

How do transaction amounts differ between fraudulent and non-fraudulent transactions??

What are the correlations between numerical features and fraud?

🤖 Modeling Approach

Preprocessing:

Used ColumnTransformer to handle categorical and numerical features.

Created time-based features (day, hour) from transaction steps.

Model Selection:

Chose XGBoost classifier for its robustness with imbalanced data.

Addressed class imbalance using scale_pos_weight and threshold tuning.

Evaluation Metrics:

Recall: Ensuring maximum frauds are detected.

Precision: Limiting false positives.

F1-Score: Balancing recall and precision.

PR-AUC: Preferred over ROC-AUC for imbalanced datasets.

📈 Key Results

The model achieved high recall, capturing the majority of fraudulent transactions.

Precision improved after class rebalancing and threshold optimization but remains a challenge due to extreme imbalance.

Fraudulent activity was concentrated in TRANSFER and CASH-OUT transactions.

Suspicious balance patterns (e.g., zero balance after transfers) were strong fraud indicators.

🚀 Future Enhancements

Incorporate advanced feature engineering (e.g., transaction velocity, network graph analysis).

Apply probability calibration for more reliable risk scoring.

Deploy the model into a real-time fraud monitoring system with streaming data.

🛠️ Tools & Technologies

Python: Data analysis and modeling

Pandas, NumPy: Data preprocessing

Matplotlib, Seaborn: Visualization

Scikit-learn: Preprocessing, evaluation metrics

XGBoost: Fraud detection model

📂 Project Structure
├── data/                  # Dataset (excluded due to size restrictions)
├── notebooks/             # Jupyter notebooks for EDA and modeling
├── README.md              # Project documentation

🙌 Acknowledgements

Dataset reference: [Kaggle - Fraud Detection Dataset].

Special thanks to the open-source community for tools and frameworks.
