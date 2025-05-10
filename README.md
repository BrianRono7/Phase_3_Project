## Telecom Customer Churn Prediction

## Project Overview
This project focuses on predicting customer churn for a telecommunications company using machine learning. By identifying customers at risk of leaving, the company can apply targeted retention strategies, reduce churn, and preserve long-term revenue. This end-to-end classification project includes data cleaning, feature engineering, modeling, evaluation, and business impact analysis.

---

## Business and Data Understanding

### Stakeholders
The primary stakeholders are the **customer retention team** and the **marketing department**. They need insights into which customers are likely to churn, what factors drive churn, and how to prioritize intervention strategies.

### Dataset
The dataset contains **3,333 telecom customer records** with **21 features**, including demographics, service plans, usage behavior, and customer service interactions. The target variable is `churn`, indicating whether a customer discontinued service.

- **Churn Rate**: 14.49% — indicating a class imbalance
- **Key Categorical Insights**:
  - Customers with **international plans** churn more frequently (42.4%) than those without (11.5%).
  - Customers with **voicemail plans** show higher loyalty (8.7% churn vs. 16.7%).
- **Key Numerical Insights**:
  - Higher day minutes and charges are associated with churn.
  - Frequent customer service calls strongly correlate with churn.

---

## Modeling

### Preprocessing
- **Outlier Handling**: Applied Winsorization to reduce the impact of extreme values.
- **Feature Engineering**: Created total usage metrics, usage-per-call ratios, and binary flags for service plans and churn-prone regions.
- **Pipelines**: Used separate pipelines for scaling numerical features and encoding categorical features.

### Models Built
- **Baseline**: Logistic Regression
- **Tuned Models**: Logistic Regression with hyperparameter tuning, Decision Tree, Random Forest, Gradient Boosting

---

## Evaluation

| Model                 | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|----------------------|----------|-----------|--------|----------|---------|
| Logistic Regression  | 87.11%   | 64.86%    | 24.74% | 35.82%   | 78.41%  |
| Tuned Logistic Reg.  | 71.21%   | 31.08%    | 80.41% | 44.83%   | 80.60%  |
| Decision Tree        | 94.60%   | 83.52%    | 78.35% | 80.85%   | 87.86%  |
| Random Forest        | **96.55%** | **100.0%** | 76.29% | 86.55%   | 90.79%  |
| Gradient Boosting    | 95.95%   | 92.68%    | 78.35% | 84.92%   | 89.41%  |

- **Selected Model**: Random Forest
- **Threshold Optimization**: Adjusted decision threshold to 0.35 to improve recall and F1-score balance

---

## Conclusion

The churn prediction model proved to be a valuable asset for the business:

- **ROI**: 585.7%
- **Estimated Savings**: $24,600 through reduced acquisition costs and retained revenue
- **Retained Customers**: ~48 via targeted interventions
- **Retention Spend**: $4,200

### Recommendations:
- Deploy the churn model in production with risk-based intervention tiers
- Introduce long-term contracts with loyalty benefits
- Implement monitoring systems to track and retrain the model quarterly
- Integrate alerts for high-risk customers into customer service tools