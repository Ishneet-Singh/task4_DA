Customer Churn Prediction – Telecom Industry

🎯 Objective
The goal of this project is to predict customer churn (whether a customer will leave the telecom service) using historical customer data. By building a machine learning model, telecom companies can:
-Identify customers at high risk of leaving.
-Take proactive measures such as offering discounts or personalized services.
-Reduce churn rate and improve customer retention.

📂 Dataset (https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data)
The dataset used is Telco Customer Churn from IBM Sample Data.
Rows: ~7,000 customers
Features: Customer demographics, account information, services subscribed, billing details, etc.
Target: Churn → Whether the customer left the service (Yes / No).

Key columns include:
gender, SeniorCitizen, Partner, Dependents
tenure, MonthlyCharges, TotalCharges
Contract, PaymentMethod, InternetService, etc.
Churn (Target variable)

⚙️ Steps in the Pipeline
Data Cleaning
Handled missing values in TotalCharges.
Dropped customerID (not useful for prediction).
Standardized categorical values like "No internet service" → "No".

Feature Encoding
Used LabelEncoder for binary columns (Yes/No, Male/Female).
Used OneHotEncoder for multi-class categorical columns (Contract, PaymentMethod, InternetService).

Feature Scaling
Applied StandardScaler to numeric features (tenure, MonthlyCharges, TotalCharges) for better model performance.

Train/Test Split
Dataset split into 80% training and 20% testing with stratification on target.

Model Training
Logistic Regression → baseline model.
Random Forest Classifier → more robust non-linear model.

Model Evaluation
Metrics used: Confusion Matrix, Precision, Recall, F1-score, ROC-AUC.
Feature importance extracted from Random Forest.

Model Saving
Final trained model saved using joblib for later deployment.


📊 Results
Logistic Regression → interpretable baseline model.
Random Forest → higher accuracy and better handling of complex relationships.

📌 Next Steps / Future Work
Hyperparameter tuning (GridSearchCV / RandomizedSearchCV).
Try advanced models: XGBoost, LightGBM, CatBoost.
Build a pipeline with sklearn.Pipeline.
Deploy as a Flask/Django API or Streamlit dashboard.
Implement real-time prediction for new customers.
ROC-AUC score indicates good separation between churned vs. non-churned customers.
Feature importance shows that tenure, contract type, monthly charges, and internet service are key churn drivers.
