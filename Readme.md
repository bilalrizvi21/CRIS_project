# Customer Retention & Churn Prediction (CRIS Project)

## Project Overview
The objective of this project is to predict customer churn for a telecom company. By identifying customers at risk of leaving, the company can take proactive measures to improve customer retention and reduce revenue loss.

## Dataset
- **Source:** Telco Customer Churn dataset
- **Size:** 7043 rows, 21 features
- **Features:** Customer demographics, account information, services subscribed, contract type, billing, and churn status
- **Data Folders:**
  - `data/raw/` : Original dataset CSV files
  - `data/processed/` : Cleaned and preprocessed datasets

## Project Workflow
1. **Exploratory Data Analysis (EDA):**
   - Analyzed churn distribution
   - Studied relationships between churn and features like tenure, contract type, internet service, and services subscribed
2. **Feature Engineering & Preprocessing:**
   - Created new features such as `num_services`, `avg_monthly_charge`, `tenure_bucket`, etc.
   - One-hot encoded categorical variables
   - Scaled numerical features
3. **Model Building & Evaluation:**
   - Baseline: Logistic Regression
   - Final Model: Random Forest Classifier
     - Tuned hyperparameters: `n_estimators=500`, `max_depth=15`, `min_samples_split=5`, `min_samples_leaf=2`
     - Handled class imbalance with `class_weight={0:1, 1:3}`
     - Adjusted prediction threshold to 0.35 for better recall on churners
   - Evaluation Metrics:
     - Accuracy, Precision, Recall, F1-score
     - ROC-AUC
     - Confusion Matrix
     - Feature Importance

## Key Insights
- Month-to-month contracts and Fiber optic internet are strongly associated with churn.
- Customers with fewer subscribed services are more likely to churn.
- Tenure is inversely correlated with churn — long-term customers are more loyal.
- TechSupport, OnlineSecurity, and Contract type are the most important features influencing churn prediction.

## Notebooks
- `1_EDA.ipynb` : Exploratory Data Analysis  
- `2_FeatureEngineering.ipynb` : Data cleaning and feature engineering  
- `3_ModelBuilding.ipynb` : Model building, evaluation, and final model selection  

## Usage
1. Clone the repository.
2. Ensure you have Python 3.x installed along with the required libraries (`pandas`, `numpy`, `scikit-learn`, `seaborn`, `matplotlib`).
3. Open and run the notebooks in the following order:
   - `1_EDA.ipynb` → `2_FeatureEngineering.ipynb` → `3_ModelBuilding.ipynb`

## Author
**Bilal Rizvi** — Final Year BS Computer Science Student  
