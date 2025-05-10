
# 📊 Telecom Customer Churn Prediction

This project uses machine learning to predict customer churn for a telecommunications company. By identifying at-risk customers, the company can implement proactive retention strategies to reduce churn, preserve revenue, and improve customer satisfaction.

## 🔍 Problem Statement

Telecom companies suffer significant losses when customers discontinue their services. Early identification of potential churners allows for targeted retention efforts. Our goal is to develop a classification model that accurately predicts churn and identifies key factors driving customer attrition.

---

## 📁 Project Structure

```
.
├── notebook.pdf                     # Data analysis and modeling notebook (PDF version)
├── Non-Technical Presentation.pptx # Business-facing summary of findings and impact
├── README.md                       # Project overview and instructions
```

---

## 🧠 Business Understanding

- **Stakeholders**: Customer retention and marketing teams.
- **Key Metric**: Maximizing recall (to capture churners), with additional focus on precision, F1-score, and ROC-AUC.
- **Churn Rate**: 14.49%, indicating a class imbalance issue.

---

## 🛠️ Data Preparation

- **Dataset**: 3,333 customer records with 21 features (demographics, service usage, plans, etc.)
- **Cleaning**: Handled outliers using Winsorization.
- **Feature Engineering**: Created usage ratios, total usage features, call categories, and boolean flags.
- **Preprocessing**: Numerical features scaled; categorical features one-hot encoded.

---

## 🤖 Models and Performance

| Model                 | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|----------------------|----------|-----------|--------|----------|---------|
| Logistic Regression  | 87.11%   | 64.86%    | 24.74% | 35.82%   | 78.41%  |
| Tuned Logistic Reg.  | 71.21%   | 31.08%    | 80.41% | 44.83%   | 80.60%  |
| Decision Tree        | 94.60%   | 83.52%    | 78.35% | 80.85%   | 87.86%  |
| Random Forest        | **96.55%** | **100.0%** | 76.29% | 86.55%   | 90.79%  |
| Gradient Boosting    | 95.95%   | 92.68%    | 78.35% | 84.92%   | 89.41%  |

- **Selected Model**: Random Forest (tuned for balance between precision and recall).
- **Optimized Threshold**: Adjusted to 0.35 to increase F1-score to 0.884.

---

## 💼 Business Impact

- **ROI**: 585.7%
- **Cost Savings**: $24,600 from retained customers
- **Estimated Retained Customers**: 48
- **Retention Cost**: $4,200

---

## ✅ Recommendations

- Implement tiered retention strategies based on churn risk.
- Revise contract offerings to improve long-term appeal.
- Integrate a churn monitoring dashboard.
- Deploy early warning systems to flag high-risk accounts.

---

## 🚀 Next Steps

- Deploy model into production with real-time inference.
- Establish periodic retraining (e.g., quarterly).
- Monitor model drift and feature importance over time.
