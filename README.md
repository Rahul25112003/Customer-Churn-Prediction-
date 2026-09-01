# Samart-customer-churn-prediction-using-ai-and-machine-learning

# PowerCo Customer Churn Prediction  
**BCG Gamma / PowerCo Case Study – Final Year Project**

## Project Overview
PowerCo, a major energy utility, is experiencing an annual customer churn rate of approximately 10%.  
The business hypothesis was that **price sensitivity** is the primary driver of churn.

This project delivers an end-to-end machine learning solution to:
1. Explore the data and validate (or challenge) the business hypothesis
2. Engineer predictive features from client and pricing data
3. Build and evaluate a Random Forest classifier to predict churn
4. Interpret model results and provide actionable insights

## Dataset
- `client_data.csv` – Customer demographics, consumption, margins, contract details
- `price_data.csv` – Historical energy and power prices (off-peak, peak, mid-peak)

## Project Structure
## Key Steps

### 1. Exploratory Data Analysis
- Overall churn rate ≈ 9.7%
- Highly skewed consumption distributions
- Churn varies significantly by sales channel and tenure
- Identified outliers and missing values (e.g., “MISSING” channel)

### 2. Feature Engineering
- **Price sensitivity features**
  - Off-peak price difference (December vs January)
  - Mean and maximum price differences across peak / mid-peak / off-peak periods
- **Tenure & contract lifecycle**
  - Tenure (years)
  - Months active, months to contract end, months since last modification / renewal
- **Transformations**
  - Log10 transformation of skewed numerical features
  - Binary encoding for `has_gas`
  - One-hot encoding for `channel_sales` and `origin_up` (rare categories filtered)

### 3. Modelling
- Algorithm: Random Forest Classifier (`n_estimators=1000`)
- Train/Test split: 75/25
- Evaluation metrics: Accuracy, Precision, Recall, Confusion Matrix
- Feature importance analysis

### Key Results
| Metric       | Value   |
|--------------|---------|
| Accuracy     | \~90.4%  |
| Precision    | \~81.8%  |
| Recall       | \~4.9%   |

**Main Insights**
- Net margin and 12-month consumption are the strongest predictors of churn
- Tenure and contract activity features are also influential
- Price sensitivity features contribute only weakly
- The original business hypothesis is **not strongly supported** by the data

## Technologies Used
- Python 3
- Pandas, NumPy
- Scikit-learn
- Seaborn & Matplotlib
- Jupyter Notebook

## How to Run
1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Place the original CSV files in the `data/` folder
4. Run the notebooks in order

## Future Improvements
- Address class imbalance (SMOTE / class weights)
- Hyperparameter tuning (GridSearchCV / Optuna)
- Try XGBoost / LightGBM
- Build a simple Streamlit dashboard for business users
- Deploy model as an API

## Author
Rahul Maji  
Final Year Project  
LinkedIn: https://www.linkedin.com/in/rahul-maji-6763a5306

---

**Disclaimer**: This is an academic project based on the publicly available BCG Gamma PowerCo case study materials. All data used is anonymised.
