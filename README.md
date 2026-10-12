```markdown
# Predicting Customer Response and Optimizing Marketing ROI 📈

This project develops an end-to-end Machine Learning pipeline to predict customer response to bank telemarketing campaigns and optimize marketing resource allocation. By combining predictive classification (will the customer subscribe?) with regression models (what is the expected ROI?), we segment the customer base to maximize campaign efficiency and conversion rates.

---

## 📋 Project Overview

Direct marketing campaigns can be highly expensive and inefficient when executed blindly. This project addresses this challenge in three major phases:
1. **Data Exploration & Preprocessing**: Clean, encode, and explore the UCI Bank Marketing Dataset to understand key demographic and behavioral correlations.
2. **Predictive Modeling**:
   * **XGBoost Classifier**: Predicts the likelihood (`P_response`) of a customer subscribing to a term deposit.
   * **XGBoost Regressor**: Estimates the financial return (`P_ROI`) based on simulated business logic utilizing call durations and campaign contact frequency.
3. **Marketing Optimization**: Groups customers into strategic segments using both model outputs to identify high-value, high-probability leads (the "Optimal Target" segment).

---

## 📊 Key Highlights & Results

### 1. Classification Performance (XGBoost)
* **Overall Accuracy**: **88.7%**
* **ROC-AUC Score**: **0.9467** (Robust performance despite highly imbalanced class distributions)
* **Class 1 (Subscription) Recall**: **87.0%** (Succeeded in capturing the vast majority of potential subscribers using class weighting via `scale_pos_weight`)

### 2. ROI Regression Performance (XGBoost)
* **Mean Absolute Error (MAE)**: **0.43**
* **R² Score**: **0.98** (High precision in predicting simulated business value)

### 3. Business Targeting Strategy Impact
* **Total Customers Analyzed**: 41,188
* **Targeted Segment Size**: **18.09%** of the customer database (7,452 customers)
* **Revenue Captured**: **39.37%** of total possible campaign revenue captured while ignoring **81.9%** of low-potential leads.
* **Outcome**: Maximizes conversion rates while dramatically reducing telemarketing operating costs.

---

## 📁 Dataset Description

This project utilizes the **Bank Marketing Dataset** from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing).
* **Instance Count**: 41,188 rows
* **Attributes**: 20 features (including client demographics, social-economic indicators, and campaign metrics)
* **Target Variable (`y`)**: Has the client subscribed to a term deposit? (`yes`/`no`)

---

## 🛠️ Tech Stack & Libraries Used

* **Language**: Python 3
* **Libraries**:
  * **Data Manipulation**: `pandas`, `numpy`
  * **Data Visualization**: `matplotlib`, `seaborn`
  * **Machine Learning**: `scikit-learn`
  * **Gradient Boosting**: `xgboost`
  * **Model Explainability**: `shap`

---

## 🚀 Getting Started

### Prerequisites
Make sure you have the required packages installed:
```bash
pip install pandas numpy matplotlib seaborn xgboost scikit-learn shap
```

### Running the Notebook
1. Clone this repository:
   ```bash
   git clone https://github.com/DhurvG/Predicting-Customer-Response-and-Optimizing-Marketing-ROI.git
   ```
2. Open `ML_Project.ipynb` in Google Colab or your local Jupyter environment.
3. Run all cells to download the dataset, train the models, and visualize the optimized marketing segments.

---

## 📈 Marketing Segmentation Categories

Customers are automatically classified into four strategic zones based on predictive thresholds:
* 🟢 **Optimal Target (High Impact)**: High subscription probability + High ROI. Focus primary campaign resources here.
* 🟡 **High Response, Low ROI**: High probability but low business value. Engage with automated or low-cost strategies.
* 🟠 **Low Response, High ROI**: High potential payoff but low conversion probability. Try alternative high-touch approaches or soft nurturing.
* ⚫ **Poor Match**: Low probability + Low ROI. Exclude from campaigns to eliminate wasted expenditure.

---

*Developed as part of a joint team effort by Ali Al Tam (Data Prep & EDA), Mohnish Kundnani (Predictive Modeling), and Dhruv Gangurde (Marketing Strategy).* 
```
