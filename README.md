

# 🏢 OASIS INFOBYTE DATA SCIENCE INTERNSHIP

## 📌 Repository: OIBSIP

Welcome to my **Data Science Internship repository at Oasis Infobyte**.
This repository contains **three end-to-end machine learning projects** demonstrating different areas of data science including:

* Predictive Modeling
* Natural Language Processing (NLP)
* Marketing Analytics

Each project follows a **complete Machine Learning pipeline**, including:

* Data preprocessing
* Exploratory Data Analysis (EDA)
* Feature engineering
* Model training and evaluation
* Model comparison
* Business insights and recommendations

---

# 👩‍💻 About Me

**Rakshita R Talegaon**
Data Science Intern – Oasis Infobyte

📧 Email: [rakshitatalegaon@gmail.com](mailto:rakshitatalegaon@gmail.com)
🔗 LinkedIn: [https://www.linkedin.com/in/rakshita-r-talegaon](https://www.linkedin.com/in/rakshita-r-talegaon)
🐙 GitHub: [https://github.com/RAKSHITART](https://github.com/RAKSHITART)

---

# 📂 Internship Tasks Completed

| #     | Task                                                  | Description                                     | Accuracy   | Key Technologies               |
| ----- | ----------------------------------------------------- | ----------------------------------------------- | ---------- | ------------------------------ |
| **3** | [Car Price Prediction](#-task-3-car-price-prediction) | Predict used car prices using regression models | **99.2%**  | Linear Regression, Optuna      |
| **4** | [Email Spam Detection](#-task-4-email-spam-detection) | Classify SMS messages as spam or ham            | **98.9%**  | NLP, Random Forest, SMOTE      |
| **5** | [Sales Prediction](#-task-5-sales-prediction)         | Predict sales from advertising spend            | **98.97%** | Lasso Regression, ROI Analysis |

---

# 🚀 Technologies Used

| Category                        | Technologies                    |
| ------------------------------- | ------------------------------- |
| **Programming**                 | Python                          |
| **Data Processing**             | Pandas, NumPy                   |
| **Visualization**               | Matplotlib, Seaborn, Plotly     |
| **Machine Learning**            | Scikit-learn, XGBoost, LightGBM |
| **Natural Language Processing** | NLTK, TextBlob, WordCloud       |
| **Hyperparameter Tuning**       | Optuna                          |
| **Imbalanced Data Handling**    | SMOTE                           |
| **Model Persistence**           | Joblib                          |

---

# 📊 TASK 1: CAR PRICE PREDICTION

## 🚗 Predict Used Car Prices

**Goal:**
Predict the selling price of used cars based on features such as **car age, fuel type, kilometers driven, transmission type, and ownership history**.

### Key Features

* **Dataset:** 299 cars
* **Features:** 9 original + 6 engineered features
* **Best Model:** Linear Regression
* **Feature Engineering:** Car age, price per kilometer, brand analysis
* **Unique Feature:** Budget recommendation system

### Results

```
R² Score : 0.9921 (99.2% accuracy)
RMSE     : ₹0.45 Lakhs
MAE      : ₹0.29 Lakhs
MAPE     : 19.65%
```

### Sample Prediction

```
Car: Honda City 2016
Actual Price: ₹8.99 Lakhs
Predicted Price: ₹8.91 Lakhs
Accuracy: 99.12%
```

📁 **View Full Details:**
[Car Price Prediction Project](./Car_Price_Prediction/README.md)

---

# 📧 TASK 2: EMAIL SPAM DETECTION

## ✉️ Spam vs Ham Classification

**Goal:**
Develop a **Natural Language Processing (NLP) model** to detect spam SMS messages while minimizing false positives.

### Key Features

* **Dataset:** 5,169 SMS messages

* **Class Distribution**

  * Ham: 87.4%
  * Spam: 12.6%

* **Best Model:** Random Forest

* **Text Representation:** TF-IDF (3000 features)

* **Feature Engineering:** 15 numerical text features

* **Class Imbalance Handling:** SMOTE

### Results

```
Accuracy   : 98.94%
Precision  : 98.39%
Recall     : 93.13%
F1 Score   : 95.69%
ROC-AUC    : 99.74%
False Positives: 2 out of 903 ham messages
```

### Confusion Matrix

```
                Predicted
                Ham   Spam
Actual Ham      903     2
Actual Spam       9   122
```

📁 **View Full Details:**
[Spam Detection Project](./Spam_Detection/README.md)

---

# 📈 TASK 3: SALES PREDICTION

## 💰 Sales Forecasting Using Advertising Spend

**Goal:**
Predict product sales using **advertising budget across TV, Radio, and Newspaper channels** to help businesses optimize marketing investments.

### Key Features

* **Dataset:** 200 advertising campaigns
* **Best Model:** Lasso Regression
* **Feature Engineering:** 10 interaction and ratio features
* **Unique Feature:** Marketing budget optimization tool

### Results

```
R² Score : 0.9897 (98.97% accuracy)
RMSE     : 0.5712
MAE      : 0.4116
MAPE     : 4.34%
```

### Optimal Budget Allocation

| Budget | TV         | Radio      | Newspaper  | Predicted Sales |
| ------ | ---------- | ---------- | ---------- | --------------- |
| $500   | $200 (40%) | $250 (50%) | $50 (10%)  | $76.65          |
| $1000  | $400 (40%) | $500 (50%) | $100 (10%) | $236.37         |

### Key Business Insight

* **TV:** Strongest correlation with sales (0.782)
* **Radio:** Highest ROI and marginal impact
* **Newspaper:** Weakest influence on sales

📁 **View Full Details:**
[Sales Prediction Project](./Sales_Prediction/README.md)

---

# 🏗️ Repository Structure

```
OIBSIP
│
├── README.md
│
├── Task3_Car_Price_Prediction
│   ├── README.md
│   ├── car_price_prediction.ipynb
│   ├── requirements.txt
│   └── car_price_model
│
├── Task4_Spam_Detection
│   ├── README.md
│   ├── spam_detection.ipynb
│   ├── requirements.txt
│   └── spam_detection_model
│
└── Task5_Sales_Prediction
    ├── README.md
    ├── sales_prediction.ipynb
    ├── requirements.txt
    └── sales_prediction_model
```

---

# 🚀 How To Use This Repository

### 1️⃣ Clone the repository

```bash
git clone https://github.com/RAKSHITART/OIBSIP.git
cd OIBSIP
```

### 2️⃣ Navigate to a specific project

```bash
cd Task5_Sales_Prediction
```

### 3️⃣ Install required packages

```bash
pip install -r requirements.txt
```

### 4️⃣ Run the notebook

```bash
jupyter notebook sales_prediction.ipynb
```

### 5️⃣ Load trained models

```python
import joblib

model = joblib.load('sales_prediction_model/best_model.pkl')
scaler = joblib.load('sales_prediction_model/scaler.pkl')
```

---

# 📊 Skills Demonstrated

| Skill                       | Projects                               |
| --------------------------- | -------------------------------------- |
| Regression                  | Car Price Prediction, Sales Prediction |
| Classification              | Spam Detection                         |
| Natural Language Processing | Spam Detection                         |
| Feature Engineering         | All Projects                           |
| Model Evaluation            | Cross-validation, learning curves      |
| Hyperparameter Optimization | Optuna                                 |
| Handling Imbalanced Data    | SMOTE                                  |
| Business Analytics          | ROI analysis, budget optimization      |
| Data Visualization          | Matplotlib, Seaborn, Plotly            |

---

# 🏆 Key Achievements

* Completed **3 end-to-end machine learning projects**
* Achieved **99%+ accuracy** across tasks
* Built **production-ready models** with saved artifacts
* Generated **business insights and recommendations**
* Applied **proper preprocessing pipelines** to avoid data leakage
* Created **well-documented project repositories**

---

# 📝 License

This project was developed as part of the **Oasis Infobyte Data Science Internship Program**.

© 2026 — Rakshita R Talegaon

---

# 📧 Contact

**Rakshita R Talegaon**
Data Science Intern – Oasis Infobyte

GitHub
[https://github.com/RAKSHITART](https://github.com/RAKSHITART)

LinkedIn
[https://www.linkedin.com/in/rakshita-r-talegaon](https://www.linkedin.com/in/rakshita-r-talegaon)

---

⭐ **If you find this repository helpful, please consider giving it a star!**

---


