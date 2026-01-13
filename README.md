# Air Quality Index (AQI) Prediction

## About
This project focuses on predicting the **Air Quality Index (AQI)** using machine learning regression techniques.  
A regression model was built using **Python and Pandas** to estimate AQI levels based on key air pollutants such as **PM2.5, PM10, NO₂, SO₂, CO, and O₃**.  

The workflow includes data cleaning, handling missing values, feature encoding, model training, and performance comparison across **Linear, Ridge, and Lasso Regression** models. Visualizations and insights are generated to support improved air quality monitoring and decision-making.

---

## Problem Context & Motivation
Air pollution is a growing concern in India, with increasing impacts on public health, including:
- Respiratory irritation  
- Chronic coughing  
- Asthma and other pollution-related diseases  

This project analyzes AQI using daily pollutant concentration data collected from air quality monitoring stations across multiple Indian cities.  
Pollutants such as **PM2.5, PM10, NO₂, SO₂, CO, and O₃** originate mainly from:
- Vehicular emissions  
- Industrial activities  
- Fuel combustion  
- Natural events  

The model also maps AQI values into categories such as:
**Good, Moderate, Poor, Very Poor, and Severe**, making the results easier to interpret and act upon.

---

## 🎯 Objective
The primary objective of this project is to **predict AQI values** using pollutant concentration data and location-based metadata.  
By leveraging **regularized linear models (Ridge and Lasso Regression)**, the project delivers:
- Interpretable predictions  
- Stable model performance  
- Actionable insights for environmental monitoring, public health alerts, and urban planning

---

## Dataset Overview
- **Source:** Kaggle  
- **Time Range:** Multiple years  
- **Original Size:** 7.3M+ records  
- **Final Sample Size:** 3,364,112 rows (after null filtering)  
- **Target Variable:** AQI (continuous)  

### Features
**Categorical Columns**
- State  
- City  
- AQI_Bucket  

**Numerical Columns**
- PM2.5, PM10  
- NO, NO₂, NOx  
- NH₃, CO, SO₂, O₃  
- Benzene, Toluene  

---

## Data Cleaning & Preprocessing
### Null Handling
- Dropped rows with missing values in key pollutant columns  
- Null percentage ranged between **16–20%** across features  

### Feature Selection
Retained the most relevant columns:
['State', 'City', 'PM2.5', 'PM10', 'NO', 'NO2', 'NOx', 'NH3',
'CO', 'SO2', 'O3', 'Benzene', 'Toluene', 'AQI_Bucket', 'AQI']


### Encoding
- Applied **Label Encoding** to categorical features:
  - State  
  - City  
  - AQI_Bucket  
- Final feature matrix **X** contains **14 predictors**

---

## Modeling Strategy
### Models Implemented
- Linear Regression  
- Lasso Regression (L1 Regularization)  
- Ridge Regression (L2 Regularization)  

### Target Variable
- **AQI (continuous)**  

### Train-Test Split
- **80/20 split** using `train_test_split`

---

## Model Performance

| Metric | Linear Regression | Lasso (α = 0.1) | Ridge (α = 0.1) |
|------|------------------|----------------|----------------|
| R² Score | 0.7962 | 0.7969 | 0.7966 |
| Train R² | 0.7967 | 0.7965 | 0.7966 |
| Test R² | 0.7962 | 0.7970 | 0.7966 |
| Generalization Gap | 0.0004 | 0.0004 | 0.0000 |

🔹 **Best Model:** Ridge Regression  
🔹 **Best R² Score:** 0.7978 (α = 0.01 after tuning)

---

## 🔍 Insights & Interpretation
- The model generalizes well across training and testing datasets  
- Very low bias and variance → **No underfitting or overfitting**  
- Ridge Regression provides the most stable and accurate predictions  
- Label Encoding proved sufficient due to low cardinality in categorical variables  

---

## Language and Library Used
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib / Seaborn  

---

## 📌 Conclusion
This project demonstrates how regression-based machine learning models can effectively predict AQI using pollutant data.  
The insights generated can help policymakers and environmental agencies take proactive steps toward improving air quality and public health.



