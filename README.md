# DSN-2025-Bootcamp-Qualification-Hackathon-Qualification

This repository contains the solution notebook for the **DSN 2025 Bootcamp Qualification Hackathon**.  
The project involves building and evaluating machine learning models to predict car prices based on given features.

---

## 📌 Project Overview
The task is a supervised regression problem:
- **Objective:** Predict the `Price` of a car.
- **Data:** The dataset includes numerical and categorical features such as `engine`, `car_age`, and `mileage_per_year`.
- **Approach:** I used data preprocessing, feature engineering, and machine learning models to make predictions.

---

## ⚙️ Methodology

1. **Exploratory Data Analysis (EDA)**  
   - Checked missing values, data types, and distributions.  
   - Examined relationships between features and the target variable.

2. **Preprocessing**  
   - Handled categorical and numerical features separately.  
   - Scaled numerical features (`engine`, `car_age`, `mileage_per_year`) using `MinMaxScaler`.  
   - Converted categorical features to strings for compatibility with CatBoost.  

3. **Modeling**  
   - Tried multiple models, including:  
     - **CatBoost Regressor**  
     - (Add other algorithms such as LightGBM, XGBoost, Linear Models)  
   - Used **K-Fold Cross-Validation** to improve robustness.  

4. **Prediction & Submission**  
   - Averaged fold predictions:  
     ```python
     y_test_pred = np.mean(test_preds, axis=0)
     ```  
   - Created a submission file:  
     ```python
     submission = pd.DataFrame({
         "id": X_test_id,
         "Price": y_test_pred
     })
     submission.to_csv("submission.csv", index=False)
     ```

---

## 📊 Dependencies

- Python 3.8+  
- Jupyter Notebook  
- NumPy  
- Pandas  
- Scikit-learn  
- CatBoost  
- Matplotlib / Seaborn (for visualization)

Install requirements with:

```bash
pip install -r requirements.txt
