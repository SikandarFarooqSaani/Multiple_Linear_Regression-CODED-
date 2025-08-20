# 🔢 Multiple Linear Regression from Scratch (and with Scikit-Learn)

This project is about implementing **Multiple Linear Regression** in two ways:  
1. Using **Scikit-Learn** (built-in implementation)  
2. Writing our **own custom class** from scratch using NumPy and linear algebra.  

We used the **Diabetes dataset** from `sklearn.datasets`.  

---

## 🚀 Project Steps

### 1. Importing Libraries
- Imported **NumPy** for linear algebra operations.  
- Imported the **Diabetes dataset** from Scikit-Learn.  

### 2. Preparing the Data
- Loaded the dataset and split it into features (**X**) and target (**y**).  
- Dataset shape:  
  - **X:** (442, 10) → 442 samples with 10 numerical features.  
- Split into **80:20 train-test ratio** with `random_state=2`.  
  - Training shape: (353, 10)  

### 3. Scikit-Learn Linear Regression
- Used `LinearRegression` from Scikit-Learn.  
- Fitted the model on training data.  
- Results:  
  - **R² Score:** `0.43`  
  - **Coefficients:** array (first: `-9.15`, last: `52.42`)  
  - **Intercept:** `151.88`  

This gave us a baseline to compare with our custom implementation.  

---

## 🛠️ Custom Linear Regression (From Scratch)

We built our own **Linear Regression class (`MyLR`)** with the following steps:  

1. **Class Initialization**  
   - `self.coef_` and `self.intercept_` set to `None`.  

2. **Fit Function**  
   - Inserted a column of 1’s at index 0 for the **intercept (β₀)**.  
   - Used the **Normal Equation**:  
     \[
     \beta = (X^T X)^{-1} X^T y
     \]  
   - Extracted `β₀` as the **intercept** and the rest as **coefficients**.  

3. **Predict Function**  
   - Took `X_test`, multiplied by coefficients, added intercept.  
   - Returned predictions.  

4. **Validation**  
   - After fitting, the **R² score, coefficients, and intercept** matched exactly with Scikit-Learn.  
   - This confirmed that Scikit-Learn also uses the **Normal Equation method** under the hood.  

---

## 📈 Results

- **R² Score (Custom & Sklearn):** `0.43`  
- **Coefficients:** Same for both methods.  
- **Intercept:** Same for both methods.  

✅ Our custom model produced **identical results** to Scikit-Learn, proving the math works!  

---

## 🛠️ Tech Stack

- **Python**  
- **NumPy**  
- **Scikit-Learn**  

---

## 📌 Conclusion

This project shows how Multiple Linear Regression works internally.  
By coding the math ourselves, we verified Scikit-Learn’s implementation and gained a deeper understanding of how linear regression models are trained and make predictions.  

---
