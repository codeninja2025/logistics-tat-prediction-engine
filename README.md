🚚 Logistics TAT Prediction Engine

Predicting Delivery Time Using Machine Learning for Operational Decision Support

🔍 Problem Statement

In logistics operations, delivery uncertainty creates:

Customer dissatisfaction

Increased support tickets

Higher inventory holding costs

SLA penalties

Operational firefighting

The key question:

Can we predict delivery time (TAT) before dispatch and reduce uncertainty in logistics operations?

This project builds an end-to-end machine learning pipeline to predict delivery time (in days) using structured shipment data.

🎯 Objective

Build a regression model that:

Predicts delivery time (in days)

Achieves high generalization performance

Aligns with operational tolerance (±2 days)

Can act as a decision-support layer for logistics teams

🧠 Approach
1️⃣ Data Preprocessing

Replaced blank values with NaN

Median imputation for numerical features

Most frequent imputation for categorical features

One-Hot Encoding (drop first to prevent dummy trap)

Standard Scaling for numerical stability

2️⃣ Model Selection

Used XGBoost Regressor because:

Handles nonlinear relationships well

Robust to multicollinearity

Performs strongly on structured tabular data

Scales well in production

Hyperparameters used:

n_estimators = 100

learning_rate = 0.1

max_depth = 5

subsample = 0.8

colsample_bytree = 0.8

3️⃣ Validation Strategy

80/20 Train-Test split

5-Fold Cross Validation

RMSE evaluation

R² evaluation

Business-aligned tolerance metric (±2 days)

📊 Results
Metric	Value
R² (Train)	0.91
R² (Test)	0.90
Mean Absolute Error	~X days
Within ±2 Days Accuracy	~93%

🔎 Interpretation:
93% of shipments are predicted within a 2-day error margin — making it practically usable for operational planning.

🏗 Architecture Overview
Raw Data
   ↓
Preprocessing Pipeline
   ↓
Feature Encoding & Scaling
   ↓
XGBoost Regressor
   ↓
Cross Validation
   ↓
Evaluation (R², RMSE, MAE, ±2 Day Accuracy)

💡 Business Impact (If Deployed)

Risk-based shipment prioritization

Dynamic SLA setting

Better CX communication

Working capital optimization

Reduction in reactive firefighting

This is not just a model —
it’s a predictive decision layer for logistics systems.

🛠 Tech Stack

Python

Pandas

NumPy

Scikit-learn

XGBoost

Matplotlib

Seaborn

🚀 Future Enhancements

Hyperparameter tuning via GridSearchCV

SHAP for feature importance explainability

Deployment via Streamlit

Real-time API integration

Drift monitoring

👨‍💻 Author

Amit Bhardwaj
IIM Indore | NIT Jalandhar
Building product-led operating systems for logistics & supply chain.
