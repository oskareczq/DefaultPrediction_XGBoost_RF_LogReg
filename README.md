# Banking Credit Risk Modeling Project

## Overview
This repository contains a comprehensive credit risk modeling solution for predicting customer defaults based on historical banking data. The model was developed as part of a credit and data analytics project for an international bank interested in modeling customer behavior and default probability.

## Dataset
The analysis is based on historical customer performance data which includes:
- **Default_data**: Contains customer exposure information with variables such as unique ID, reporting date, days past due (DPD), relative time to maturity (TtM), and default indicators
- **GDP_data**: Contains macroeconomic indicators represented by yearly GDP values

## Methodology

### Data Preprocessing
- Data cleaning and handling of missing values
- Feature engineering to create relevant predictors from raw data
- Transformation of nominal GDP values into growth rates
- Standardization of numerical features to ensure model stability

### Exploratory Data Analysis (EDA)
- Analysis of default rates across different time periods
- Examination of default rates by DPD buckets (0 DPD, 1-30 DPD, 31-60 DPD, 61-90 DPD)
- Investigation of the relationship between macroeconomic factors and default rates
- Correlation analysis between features

### Class Imbalance Handling
- Implementation of SMOTE (Synthetic Minority Over-sampling Technique) to address class imbalance in the default data
- Comparative analysis of model performance with and without SMOTE

### Modeling Approaches
Multiple modeling techniques were implemented and compared:
1. **Logistic Regression**: Baseline model with interpretable coefficients
2. **Random Forest**: Ensemble method to capture non-linear relationships
3. **XGBoost**: Gradient boosting approach for improved predictive performance

### Model Evaluation
- Performance assessment using confusion matrices
- ROC curves and AUC scores
- Precision, recall, and F1 scores
- Comparison of predicted vs. realized default probabilities

### Model Interpretability
- SHAP (SHapley Additive exPlanations) values to understand feature importance
- Variable importance plots to identify key predictors of default
- Partial dependence plots to visualize feature effects on predictions

## Results
The repository includes detailed analysis of:
- Default rate trends over time
- The impact of DPD buckets on default probability
- Relative performance of different modeling approaches
- Key predictors of customer default
- Model validation and robustness tests

## Key Findings
- Default rates show significant variation across different DPD buckets, with higher DPD values strongly correlated with increased default probability
- Macroeconomic factors (GDP growth rates) demonstrate cyclical relationship with default patterns
- The most predictive features include:
  - **DPD** (Days Past Due): Strong indicator of customer payment behavior
  - **Yearly Growth**: Macroeconomic indicator showing impact of economic cycles
  - **is_crisis**: Binary feature indicating economic downturn periods
  - **TtM_bucket_Krótkoterminowy**: Short-term maturity bucket feature
- The XGBoost model achieved the highest overall performance with an **AUC of 0.86** on the test set

## Dependencies
Main libraries and frameworks used:
- pandas, numpy for data manipulation
- scikit-learn for modeling and evaluation
- imbalanced-learn for SMOTE implementation
- xgboost for gradient boosting models
- matplotlib, seaborn for visualization
- shap for model interpretability