# Waze User Churn Prediction

End-to-end data analytics project completed as part of the **Google Advanced Data Analytics Professional Certificate**.

In this project, I worked with **Waze’s data team** to analyze user behavior and build models that can help predict user churn.

The project follows the complete data analytics lifecycle in three clear stages:  
**Statistical Analysis → Logistic Regression → Machine Learning Classification**.

---

## Project Overview

**Main Research Question:**  
Do iPhone users and Android users have the same average number of drives?

### 1. Statistical Analysis (Hypothesis Testing)
- Compared the average number of drives between iPhone and Android users using an independent two-sample t-test.
- **Result:** No statistically significant difference was found (p-value > 0.05).
- This showed that device type alone does not strongly influence driving activity.

### 2. Logistic Regression
- Built a logistic regression model to predict whether a user will churn (`label`).
- Important findings:
  - `activity_days` was the strongest predictor and had a clear negative relationship with churn.
  - The engineered feature `professional_driver` also ranked among the top predictors.
  - `km_per_driving_day` looked important in the correlation heatmap but became one of the least useful features in the actual model.
- **Conclusion:** The model provides useful insights but is not strong enough (especially in recall) to support high-stakes business decisions on its own.

### 3. Machine Learning Classification
- Trained and compared **Random Forest** and **XGBoost** models.
- Used a proper train-validation-test split for reliable model selection and final evaluation.
- Engineered features made up more than half of the top 10 most important predictors.
- **Best performing model:** XGBoost
- **Conclusion:** Overall predictive power is moderate. Recall is still a limitation.  
  The model is best used to guide further analysis and feature engineering rather than make final churn-prevention decisions.

**Recommended Next Steps:**
- Create more detailed features (for example: time of day or location patterns).
- Collect richer in-app behavior data (such as how often users report or confirm road hazards).

---

## Key Trade-offs Considered

| Method                        | Advantage                          | Limitation                          |
|------------------------------|------------------------------------|-------------------------------------|
| Logistic Regression          | Easy to interpret                  | Lower predictive accuracy           |
| Random Forest / XGBoost      | Better predictive performance      | Harder to interpret                 |
| Train / Validation / Test    | More reliable final evaluation     | Slightly less data for training     |

---

## Tools & Technologies

| Category              | Tools Used                            |
|-----------------------|---------------------------------------|
| Data Manipulation     | pandas, NumPy                         |
| Visualization         | Matplotlib, Seaborn                   |
| Statistics            | SciPy                                 |
| Machine Learning      | scikit-learn, XGBoost                 |
| Model Evaluation      | GridSearchCV, classification metrics  |

---

## Repository Structure
