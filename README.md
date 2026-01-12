# NHANES Fasting Glucose Prediction

**Author:** Robert Giurcanu  
**Date:** November 2025  

---

## Overview
This project predicts fasting glucose levels using NHANES 2021–2023 data. Two models were implemented:

- **Linear Regression**
- **Random Forest Regression**  

The goal is to compare model performance and understand which features (age, BMI, diabetes status, and dietary intake) most influence glucose levels.

---

## Data

- **Demographics:** Age, Sex (`DEMO_L.XPT`)  
- **Glucose & Biomarkers:** Fasting glucose (`GLU_L.XPT`), HbA1c (`GHB_L.XPT`)  
- **Dietary Intake:** Calories, Protein, Carbs, Sugar, Fiber, Fats, Cholesterol, Sodium, Potassium (`DR1TOT_L.XPT`)  
- **Body Measures:** BMI, Waist circumference (`BMX_L.XPT`)  
- **Diabetes Status:** Diabetes diagnosis (`DIQ_L.XPT`)  

---

## Results

| Metric | Linear Regression | Random Forest |
|--------|-----------------|---------------|
| R² | 0.33 | 0.36 |
| MSE | 773 | 731 |
| Clinical Accuracy (within 10%) | 68% | 66% |
| Clinical Accuracy (within 15%) | 81% | 79% |

**Important Features:**  
Diabetes status, waist circumference, and age were the strongest predictors in both models. Other variables, like calories, sex, and prediabetes status, were of less influence.

Residual analysis shows Random Forest predictions are generally centered around zero, while linear regression shows larger deviations for mid-high glucose values (~140–170 mg/dL).

---

## Notebook

All tables, plots, and detailed discussion are available in the notebook: `NHANES_Fasting_Glucose.ipynb`.

---

## Dependencies

- Python 3  
- pandas, numpy, matplotlib, scikit-learn, tableone
