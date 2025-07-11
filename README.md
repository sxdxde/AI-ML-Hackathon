# AI-ML-Hackathon

# 🔌 Electricity Bill Prediction using Machine Learning

This project aims to build an intelligent, interactive system to **predict monthly electricity bills** based on home appliance usage, tariff rates, utility provider, and location. Leveraging supervised machine learning, the model provides accurate, interpretable insights into energy consumption patterns for both households and utility companies.

---

## 🧠 Problem Statement

Accurately forecasting electricity bills can help **households budget their expenses**, identify **high-consumption devices**, and allow **utility providers to anticipate demand**. This project takes in appliance usage and contextual data and predicts the **monthly electricity bill** using regression-based machine learning models.

---

## 📊 Dataset Description

The dataset includes the following features:

| Column Name       | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| Fan               | Number of fans in the household (int)                                      |
| Refrigerator      | Number of refrigerators (float)                                             |
| AirConditioner    | Number of air conditioners (float)                                          |
| Television        | Number of televisions (float)                                               |
| Monitor           | Number of computer monitors (float)                                         |
| MotorPump         | Number of motor pumps (int)                                                 |
| Month             | Month of billing (1 = Jan, ..., 12 = Dec)                                   |
| City              | City where the household is located (categorical)                           |
| Company           | Electricity provider name (categorical)                                     |
| MonthlyHours      | Appliance usage in hours for the month (int)                                |
| TariffRate        | Tariff per kWh in ₹ (float)                                                 |
| ElectricityBill   | **Target variable** — actual electricity bill for the month in ₹ (float)    |

---

## ⚙️ Machine Learning Models Used

The following regression models were trained and evaluated:

1. **Linear Regression**  
   - Baseline model assuming a linear relationship between features and the target.
   - Fast and interpretable but limited in capturing non-linear patterns.

2. **Random Forest Regressor**  
   - Ensemble of decision trees using bootstrapped samples.
   - Handles non-linearities, reduces overfitting, and provides robust predictions.

3. **Gradient Boosting Regressor**  
   - Builds trees sequentially, correcting previous errors.
   - Delivers high accuracy but is more sensitive to hyperparameters.

Each model was evaluated using the following metrics:
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- R² Score (Variance Explained)
- MAPE (Mean Absolute Percentage Error)

---

## 🧼 Data Cleaning & Preprocessing

- Missing values handled via imputation or filtering.
- Categorical columns (`City`, `Company`) encoded using one-hot encoding.
- Features scaled for Linear Regression.
- Month encoded using sin/cos cyclic encoding for temporal continuity.
- Feature/target leakage was explicitly avoided by ensuring test data was untouched during training.

---

## 📈 Data Visualization

- Heatmaps of correlation matrices.
- Residual plots for model diagnostics.
- Bar plots comparing model metrics.
- Scatter plots for predicted vs actual values.
- Error distributions and radar charts for performance comparison.

---

## 🔧 Feature Engineering

- Appliance usage combined with `MonthlyHours` and `TariffRate` to derive usage-based cost implications.
- Temporal (Month) encoding for seasonal effects.
- Categorical feature expansion through one-hot encoding.

---

## 🚉 Model Training & Testing

- Train/test split of 80/20.
- Separate scaling used for Linear Regression to prevent leakage.
- All models trained independently and compared under identical test conditions.

---

## 🖥️ Interactive UI

An **interactive Jupyter interface** (using `ipywidgets`) is included that allows:
- Inputting appliance counts, city, company, tariff rate, and monthly usage
- Viewing live predictions from all three models
- Visualizing how usage changes affect bill outcomes

---

## 📌 Results Summary

| Model              | R² Score | MAE (₹) | RMSE (₹) |
|--------------------|----------|---------|----------|
| Linear Regression  | 0.9956   | 49.27   | 70.56    |
| Random Forest      | 1.0000   | 1.55    | 5.66     |
| Gradient Boosting  | 0.9996   | 17.77   | 22.64    |

> While **Random Forest** performed best in this dataset, performance may vary depending on feature distributions, so all models are available for comparison.

---

## ✅ Key Takeaways

- Interactive system for real-time electricity bill prediction
- Accurate forecasting using ensemble models
- Insight into high-consumption appliances
- Scalable and user-friendly design

---

## 🚀 Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/electricity-bill-predictor.git
   cd electricity-bill-predictor
