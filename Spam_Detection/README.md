# 📧 EMAIL SPAM DETECTION WITH MACHINE LEARNING

---

## 🎯 PROJECT OVERVIEW

Built a machine learning model to classify SMS/Email messages as **Spam** or **Ham (non-spam)**.  
The model uses advanced NLP techniques and ensemble learning to achieve high accuracy.

---

## 📊 DATASET

- **Source**: SMS Spam Collection Dataset (Kaggle)  
- **Total Messages**: 5,169  
- **Classes**: Ham (4,516), Spam (653)  
- **Class Distribution**: 87.4% Ham, 12.6% Spam  

---

## 🔧 TECHNOLOGIES USED

| Category | Technologies |
|----------|-------------|
| **Programming** | Python 3.x |
| **Data Processing** | Pandas, NumPy, NLTK |
| **Visualization** | Matplotlib, Seaborn, WordCloud |
| **Machine Learning** | Scikit-learn, XGBoost, LightGBM |
| **Imbalance Handling** | SMOTE |
| **Model Persistence** | Joblib |

---

## 🏗️ PROJECT STRUCTURE

```
Task4_Spam_Detection/
│
├── spam_detection.ipynb        # Complete notebook with all blocks
├── requirements.txt            # Required Python packages
│
└── spam_detection_model/       # Saved model artifacts
    ├── best_model.pkl          # Trained classifier
    ├── tfidf_vectorizer.pkl    # TF-IDF vectorizer
    ├── scaler.pkl              # Feature scaler
    ├── feature_names.pkl       # Numerical feature names
    └── model_results.pkl       # Model comparison results
```

---

## 📝 NOTEBOOK STRUCTURE (16 Blocks)

| Block | Section | Description |
|------|---------|-------------|
| 1 | Installation | Required packages |
| 2 | Imports | Library imports |
| 3 | Load Data | Dataset loading |
| 4 | Preprocessing | Data cleaning |
| 5 | EDA | Exploratory analysis |
| 6 | Text Cleaning | Preprocessing function |
| 7 | Feature Engineering | TF-IDF + numerical features |
| 8 | Train-Test Split | Data splitting |
| 9 | SMOTE | Class imbalance handling |
| 10 | Model Training | Multiple models + ensemble |
| 11 | Evaluation | Performance metrics |
| 12 | Error Analysis | Misclassification analysis |
| 13 | Save Model | Export artifacts |
| 14 | Prediction Function | Reusable predictor |
| 15 | Test Predictions | Demo with real messages |
| 16 | Summary | Project summary |

---

## 📈 MODEL PERFORMANCE

### Best Model: **Random Forest**

| Metric | Score |
|------|------|
| Accuracy | 98.94% |
| Precision | 98.39% |
| Recall | 93.13% |
| F1-Score | 95.69% |
| ROC-AUC | 99.74% |

### Confusion Matrix (Test Set)

| Actual / Predicted | Ham | Spam |
|--------------------|-----|------|
| **Ham** | 903 | 2 |
| **Spam** | 9 | 122 |

- **False Positives**: 2 (Ham classified as Spam)  
- **False Negatives**: 9 (Spam classified as Ham)

---

## 🧠 KEY FEATURES ENGINEERED

### TF-IDF Features (3000)

- Unigrams and bigrams  
- Min document frequency: 2  
- Max document frequency: 95%  

### Numerical Features (15)

1. Message Length  
2. Word Count  
3. Capital Letter Count  
4. Digit Count  
5. Exclamation Mark Count  
6. Question Mark Count  
7. Has URL (binary)  
8. Has Number (binary)  
9. Has Currency Symbol (binary)  
10. Has Prize-related Words (binary)  
11. Has Urgent Words (binary)  
12. Has Money-related Words (binary)  
13. Has Free/Offer Words (binary)  
14. Capital Ratio  
15. Digit Ratio  

---

## 🚀 HOW TO RUN

### 1️⃣ Clone the repository

```bash
git clone https://github.com/yourusername/OIBSIP.git
cd OIBSIP/Task4_Spam_Detection
```

### 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the notebook

```bash
jupyter notebook spam_detection.ipynb
```

### 4️⃣ Use the saved model for predictions

```python
import joblib
import re
import numpy as np
from scipy.sparse import hstack, csr_matrix

# Load model artifacts
model = joblib.load('spam_detection_model/best_model.pkl')
vectorizer = joblib.load('spam_detection_model/tfidf_vectorizer.pkl')
scaler = joblib.load('spam_detection_model/scaler.pkl')
feature_names = joblib.load('spam_detection_model/feature_names.pkl')

# Define prediction function (copy from notebook Block 14)
def predict_spam(message):
    # ... (function code here)
    return prediction, confidence

# Test
predict_spam("Congratulations! You've won $1000!")
```

---

## 📊 SAMPLE PREDICTIONS

| Message | Actual | Predicted | Confidence |
|-------|-------|----------|-----------|
| Congratulations! You've won $1000! | Spam | SPAM | 98% |
| Hey, meeting at 3pm? | Ham | HAM | 100% |
| URGENT: Account suspended | Spam | SPAM | 95% |
| Thanks for your email | Ham | HAM | 92% |
| FREE MONEY!!! Call now! | Spam | SPAM | 97% |

---

## 🎯 KEY ACHIEVEMENTS

✅ 98.9% accuracy on test data  
✅ Only 2 false positives out of 903 ham messages  
✅ Successfully handled class imbalance with SMOTE  
✅ Created 15 custom numerical features  
✅ Implemented ensemble of 4 ML algorithms  
✅ Production-ready prediction function  
✅ Complete ML pipeline from data to deployment  

---

## 📚 REFERENCES

- Scikit-learn Documentation  
  https://scikit-learn.org/stable/

- NLTK Documentation  
  https://www.nltk.org/

- SMS Spam Collection Dataset  
  https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset

---

## 📧 CONTACT

**Rakshita R Talegaon**  
Data Science Intern - Oasis Infobyte  

GitHub: https://github.com/RAKSHITART  
LinkedIn: www.linkedin.com/in/rakshita-r-talegaon 

---

## 📄 LICENSE

This project is created for internship purposes at **Oasis Infobyte**.

© 2026 Oasis Infobyte
