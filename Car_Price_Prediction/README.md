# 🚗 CAR PRICE PREDICTION WITH MACHINE LEARNING

## 🎯 PROJECT OVERVIEW

Built a machine learning model to predict the selling price of cars based on various features like year, present price, kilometers driven, fuel type, transmission, and more. The model achieves **99.2% accuracy** on test data.

---

## 📊 DATASET

- **Source**: Car Price Prediction Dataset  
- **Total Samples**: 299 cars (after cleaning)  
- **Features**: 9 original + 6 engineered features  
- **Target**: Selling Price (in Lakhs, 1 Lakh = ₹100,000)

### Original Features

- CarName  
- Year  
- Present_Price  
- Driven_kms  
- Fuel_Type  
- Selling_type  
- Transmission  
- Owner  

### Engineered Features

- CarBrand  
- CarAge  
- Price_per_Year  
- Price_per_KM  
- Brand_Type  
- Trans_Owner  

---

## 🔧 TECHNOLOGIES USED

| Category | Technologies |
|----------|-------------|
| **Programming** | Python 3.x |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-learn, XGBoost, LightGBM, CatBoost |
| **Hyperparameter Tuning** | Optuna |
| **Model Persistence** | Joblib |

---

## 🏗️ PROJECT STRUCTURE

```
Task3_Car_Price_Prediction/
│
├── README.md                       # This file
├── car_price_prediction.ipynb      # Complete notebook with all blocks
├── requirements.txt                # Required Python packages
│
└── car_price_model/                # Saved model artifacts
    ├── best_model.pkl              # Trained Linear Regression model
    ├── preprocessor.pkl            # Fitted preprocessor (Scaler + OneHot)
    ├── numerical_cols.pkl          # List of numerical column names
    ├── categorical_cols.pkl        # List of categorical column names
    └── feature_names.pkl           # All feature names after encoding
```

---

## 📝 NOTEBOOK STRUCTURE (20 Blocks)

| Block | Section | Description |
|------|---------|-------------|
| 1 | Installation | Required packages |
| 2 | Imports | Library imports |
| 3 | Load Data | Dataset loading |
| 4 | Preprocessing | Data cleaning |
| 5 | Feature Engineering | Create new features |
| 6 | EDA | Exploratory analysis |
| 7 | Data Preparation | Train-test split |
| 8 | Preprocessing Pipeline | Fit on training only |
| 9 | Feature Selection | Mutual information |
| 10 | Model Definitions | 12 ML models |
| 11 | Model Training | Cross-validation |
| 12 | Hyperparameter Tuning | Optuna optimization |
| 13 | Ensemble Models | Voting & Stacking |
| 14 | Model Evaluation | Test set performance |
| 15 | Feature Importance | Coefficient analysis |
| 16 | Prediction Function | Reusable predictor |
| 17 | Test Predictions | Demo with real cars |
| 18 | Budget Recommendation | Find cars within budget |
| 19 | Learning Curves | Overfitting analysis |
| 20 | Save Model | Export artifacts |

---

## 📈 MODEL PERFORMANCE

### Best Model: **Linear Regression**

| Metric | Value | Interpretation |
|------|------|---------------|
| **R² Score** | 0.9921 | 99.2% accuracy |
| **RMSE** | ₹0.45 Lakhs | ₹45,000 average error |
| **MAE** | ₹0.29 Lakhs | ₹29,000 average absolute error |
| **MAPE** | 19.65% | 19.65% percentage error |

### Performance on Test Samples

```
Car: city (2016)
Actual: ₹8.99L → Predicted: ₹8.91L (99.12% accuracy)

Car: brio (2015)
Actual: ₹5.25L → Predicted: ₹5.05L (96.15% accuracy)

Car: Royal Enfield (2015)
Actual: ₹1.11L → Predicted: ₹1.11L (99.60% accuracy)
```

---

## 🧠 KEY FEATURES & THEIR IMPACT

### Top Positive Influences (Increase Price)

| Feature | Impact |
|-------|-------|
| **present_price** | +₹0.85L per 1L increase |
| **Year** | +₹0.32L per year newer |
| **fuel_type_Diesel** | +₹0.28L compared to Petrol |

### Top Negative Influences (Decrease Price)

| Feature | Impact |
|-------|-------|
| **driven_kms** | -₹0.15L per 10,000 km driven |
| **transmission_Manual** | -₹0.15L compared to Automatic |
| **Owner** | -₹0.12L per additional owner |

---

## 🎯 BUDGET RECOMMENDATION SYSTEM

The model includes a budget recommendation feature that finds cars within your budget:

```python
# Find cars around ₹5 Lakhs (₹500,000)
recommendations = get_car_recommendation(5.0, best_model, preprocessor, X_train, y_train)
```

### Sample Output

```
Budget: ₹5.0 Lakhs (₹500,000)

- verna (2013): ₹4.99L
- corolla altis (2010): ₹5.01L
- grand i10 (2015): ₹5.03L
```

---

## 🚀 HOW TO USE

### 1️⃣ Clone the repository

```bash
git clone https://github.com/RAKSHITART/OIBSIP.git
cd OIBSIP/Task3_Car_Price_Prediction
```

### 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the notebook

```bash
jupyter notebook car_price_prediction.ipynb
```

### 4️⃣ Use the saved model for predictions

```python
import joblib
import pandas as pd

# Load model artifacts
model = joblib.load('car_price_model/best_model.pkl')
preprocessor = joblib.load('car_price_model/preprocessor.pkl')

# Create car features
car = {
    'Year': 2015,
    'present_price': 8.5,
    'driven_kms': 50000,
    'fuel_type': 'Petrol',
    'selling_type': 'Dealer',
    'transmission': 'Manual',
    'Owner': 1,
    'CarName': 'Swift',
    'CarBrand': 'maruti',
    'CarAge': 11,
    'Price_per_Year': 8.5/12,
    'Price_per_KM': 8.5/51,
    'Brand_Type': 'maruti_Petrol',
    'Trans_Owner': 'Manual_1'
}

# Predict
input_df = pd.DataFrame([car])
processed = preprocessor.transform(input_df)
price = model.predict(processed)[0]

print(f"Predicted Price: ₹{price:.2f} Lakhs")
```

---

## 📊 KEY ACHIEVEMENTS

✅ **99.2% accuracy** on test data  
✅ **12 ML models** compared and evaluated  
✅ **No data leakage** — preprocessor fitted on training only  
✅ **6 engineered features** to improve performance  
✅ **Optuna hyperparameter tuning** for top models  
✅ **Ensemble methods** (Voting & Stacking)  
✅ **Budget recommendation system**  
✅ **Production-ready prediction function**  
✅ **Complete ML pipeline from data to deployment**

---

## 📈 LEARNING CURVE INSIGHTS

```
Training Size Analysis

20% → Test R²: 0.9735
40% → Test R²: 0.9765  
60% → Test R²: 0.9840
80% → Test R²: 0.9898
90% → Test R²: 0.9912
```

**Conclusion:** Model is well-fitted with minimal overfitting (gap < 0.01)

---

## 📚 REFERENCES

Scikit-learn Documentation  
https://scikit-learn.org/

Optuna Documentation  
https://optuna.org/

Car Price Prediction Dataset  
https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho

---

## 📧 CONTACT

**Rakshit Art**  
Data Science Intern - Oasis Infobyte  

GitHub: https://github.com/RAKSHITART  
LinkedIn:www.linkedin.com/in/rakshita-r-talegaon 

---

## 📄 LICENSE

This project is created for internship purposes at **Oasis Infobyte**.

© 2026 Oasis Infobyte
