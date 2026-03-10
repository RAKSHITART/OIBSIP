# 📊 SALES PREDICTION WITH MACHINE LEARNING

## 🎯 PROJECT OVERVIEW

Built a machine learning model to predict **product sales** based on advertising spend across TV, Radio, and Newspaper channels. The model helps businesses optimize their marketing budget for maximum return on investment (ROI).

### Business Problem

Companies need to know how to allocate their advertising budget across different channels to maximize sales. This project provides data-driven recommendations for optimal budget allocation.

---

## 📊 DATASET

- **Source**: Advertising Dataset (TV, Radio, Newspaper spend vs Sales)  
- **Total Samples**: 200  
- **Features**: 3 original + 10 engineered features  
- **Target**: Sales (in thousands of dollars)

### Original Features

- `TV`: TV advertising budget ($)  
- `Radio`: Radio advertising budget ($)  
- `Newspaper`: Newspaper advertising budget ($)

### Engineered Features

- Interaction terms: `TV_Radio`, `TV_Newspaper`, `Radio_Newspaper`  
- Budget ratios: `TV_Ratio`, `Radio_Ratio`, `Newspaper_Ratio`  
- Total spend: `Total_Spend`  
- ROI indicators: `TV_ROI`, `Radio_ROI`, `Newspaper_ROI`

---

## 🔧 TECHNOLOGIES USED

| Category | Technologies |
|----------|-------------|
| **Programming** | Python 3.x |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn, Plotly |
| **Machine Learning** | Scikit-learn, XGBoost, LightGBM |
| **Regularization** | Lasso, Ridge, ElasticNet |
| **Model Persistence** | Joblib |

---

## 🏗️ PROJECT STRUCTURE

```
Task5_Sales_Prediction/
│
├── sales_prediction.ipynb        # Complete notebook with all blocks
├── README.md                     # This file
├── requirements.txt              # Required Python packages
│
└── sales_prediction_model/       # Saved model artifacts
    ├── best_model.pkl            # Trained Lasso Regression model
    ├── scaler.pkl                # Fitted StandardScaler
    ├── feature_names.pkl         # List of all 13 features
    ├── test_results.pkl          # Model performance metrics
    └── model_info.pkl            # Summary information
```

---

## 📝 NOTEBOOK STRUCTURE (20+ Blocks)

| Block | Section | Description |
|------|---------|-------------|
| 1 | Installation | Required packages |
| 2 | Imports | Library imports |
| 3 | Load Data | Dataset loading |
| 4 | Preprocessing | Data cleaning |
| 5 | EDA | Exploratory analysis |
| 6 | Advanced Visualizations | 3D plots, bubble charts, etc. |
| 7 | Feature Engineering | Create 10 new features |
| 8 | Data Preparation | Train-test split & scaling |
| 9 | Model Definitions | 12 ML models |
| 10 | Model Training | Cross-validation |
| 11 | Overfitting Check | Train vs Test comparison |
| 12 | Ensemble Models | Voting & Stacking |
| 13 | Model Evaluation | Test set performance |
| 14 | Feature Importance | Coefficient analysis |
| 15 | Marketing Insights | ROI & budget analysis |
| 16 | Prediction Function | Reusable predictor |
| 17 | Budget Optimization | Find optimal allocation |
| 18 | Learning Curve | Overfitting analysis |
| 19 | Business Scenarios | Real-world testing |
| 20 | Save Model | Export artifacts |

---

## 📈 MODEL PERFORMANCE

### Best Model: **Lasso Regression (L1 Regularization)**

| Metric | Score | Interpretation |
|------|------|---------------|
| **R² Score** | 0.9897 | 98.97% accuracy |
| **RMSE** | 0.5712 | Average error: $571 |
| **MAE** | 0.4116 | Average absolute error: $412 |
| **MAPE** | 4.34% | Percentage error |

### Comparison with Other Models

| Model | R² Score | Rank |
|------|---------|------|
| **Lasso Regression** | **0.9897** | 🥇 1st |
| Linear Regression | 0.9894 | 🥈 2nd |
| Extra Trees | 0.9893 | 🥉 3rd |
| ElasticNet | 0.9891 | 4th |
| Ridge Regression | 0.9888 | 5th |
| Random Forest | 0.9875 | 6th |
| XGBoost | 0.9865 | 7th |
| Gradient Boosting | 0.9856 | 8th |

---

## 🧠 FEATURE IMPORTANCE ANALYSIS

### Top Features Impacting Sales

| Feature | Coefficient | Impact per $100 |
|--------|-------------|----------------|
| **Radio** | +1.295 | +$129.53 |
| **TV_Radio (interaction)** | +2.940 | Indirect effect |
| **Total_Spend** | +0.813 | +$81.34 |
| **TV_Ratio** | +0.566 | +$56.60 |

### Key Insight

Radio has the highest marginal impact, while TV provides strong baseline correlation.

---

## 📊 MARKETING INSIGHTS & ROI ANALYSIS

### Average Spend & Sales

```
TV Spend:        $147.04
Radio Spend:     $23.26
Newspaper Spend: $30.55
Sales:           $14.02
```

### Correlation with Sales

| Channel | Correlation | Strength |
|--------|-------------|---------|
| **TV** | 0.782 | **Strong** |
| **Radio** | 0.576 | Moderate |
| **Newspaper** | 0.228 | Weak |

### ROI per Dollar Spent

| Channel | ROI | Efficiency |
|--------|-----|-----------|
| Radio | $0.60 | **Most Efficient** |
| Newspaper | $0.46 | Moderate |
| TV | $0.10 | Least Efficient |

---

## 💰 BUDGET OPTIMIZATION RESULTS

### Optimal Allocation for Any Budget

| Budget | TV | Radio | Newspaper | Predicted Sales |
|------|----|------|-----------|----------------|
| $100 | $50 (50%) | $40 (40%) | $10 (10%) | $11.24 |
| $200 | $80 (40%) | $100 (50%) | $20 (10%) | $22.86 |
| $500 | $200 (40%) | $250 (50%) | $50 (10%) | $76.65 |
| $1000 | $400 (40%) | $500 (50%) | $100 (10%) | $236.37 |

### 📌 Key Finding

The optimal ratio converges to **40% TV, 50% Radio, 10% Newspaper** across all budget sizes.

---

## 🎯 FINAL BUSINESS RECOMMENDATION

```
Based on comprehensive analysis of 200 campaigns:

RECOMMENDED BUDGET ALLOCATION

TV:        40%  (maintain strong baseline)
Radio:     50%  (maximize ROI)
Newspaper: 10%  (minimize)

Why this works:
✓ TV has strongest correlation with sales (0.782)
✓ Radio has highest marginal impact
✓ Newspaper shows weakest performance
✓ TV + Radio interaction boosts sales further
```

---

## 🚀 HOW TO USE

### 1️⃣ Clone the repository

```bash
git clone https://github.com/RAKSHITART/OIBSIP.git
cd OIBSIP/Task5_Sales_Prediction
```

### 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the notebook

```bash
jupyter notebook sales_prediction.ipynb
```

### 4️⃣ Use the saved model for predictions

```python
import joblib
import numpy as np

model = joblib.load('sales_prediction_model/best_model.pkl')
scaler = joblib.load('sales_prediction_model/scaler.pkl')

def predict_sales(tv, radio, newspaper):
    total = tv + radio + newspaper
    tv_radio = tv * radio
    tv_newspaper = tv * newspaper
    radio_newspaper = radio * newspaper
    tv_ratio = tv / total if total > 0 else 0
    radio_ratio = radio / total if total > 0 else 0
    newspaper_ratio = newspaper / total if total > 0 else 0
    tv_roi = 15 / (tv + 1)
    radio_roi = 15 / (radio + 1)
    newspaper_roi = 15 / (newspaper + 1)

    features = np.array([[tv, radio, newspaper, tv_radio, tv_newspaper,
                          radio_newspaper, tv_ratio, radio_ratio,
                          newspaper_ratio, total, tv_roi,
                          radio_roi, newspaper_roi]])

    features_scaled = scaler.transform(features)
    return model.predict(features_scaled)[0]

sales = predict_sales(200, 100, 50)
print(f"Predicted Sales: ${sales:.2f}")
```

Output:

```
Predicted Sales: $36.55
```

---

## 📊 SAMPLE PREDICTIONS

| TV Spend | Radio Spend | Newspaper Spend | Predicted Sales |
|---------|------------|----------------|----------------|
| $100 | $50 | $25 | $16.85 |
| $200 | $100 | $50 | $36.55 |
| $300 | $75 | $40 | $38.00 |
| $50 | $25 | $10 | $9.65 |

---

## 📈 LEARNING CURVE ANALYSIS

```
Training R²: 0.9957
CV R²:       0.9927
Gap:         0.0031
```

✅ **Model Status:** Well-fitted (Excellent)  
The small gap between training and cross-validation scores indicates **no overfitting**.

---

## 🎯 KEY ACHIEVEMENTS

✅ **98.97% accuracy** with Lasso Regression  
✅ **12 ML models** compared and evaluated  
✅ **10 engineered features** to capture interactions  
✅ **Optimal budget allocation** for any budget size  
✅ **ROI analysis** for each advertising channel  
✅ **Overfitting check** with learning curves  
✅ **Production-ready prediction function**  
✅ **Business-friendly recommendations**  
✅ **Complete ML pipeline** from data to deployment  

---

## 📚 REFERENCES

Scikit-learn Documentation  
https://scikit-learn.org/stable/

Advertising Dataset  
https://www.kaggle.com/datasets/ashydv/advertising-dataset

Lasso Regression Explained  
https://en.wikipedia.org/wiki/Lasso_(statistics)

---

## 📧 CONTACT

**Rakshita R Talegaon**  
Data Science Intern — Oasis Infobyte  

GitHub: https://github.com/RAKSHITART  
LinkedIn: https://www.linkedin.com/in/rakshita-r-talegaon

---

## 📄 LICENSE

This project is created for internship purposes at **Oasis Infobyte**.

© 2026 Oasis Infobyte
