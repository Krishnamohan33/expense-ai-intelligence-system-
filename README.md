# Expense AI Intelligence System

**Author:** Krishnamohan Yagneswaran

---

## Overview

This project is a machine learning system that analyzes expense data and provides useful financial insights. It combines multiple models to predict spending, detect risk, classify transactions, and understand user behavior.

The system is designed to work with real-world expense data and help users make better financial decisions.

---

## ⚠️ Important Notes

* This repository contains **trained `.pkl` model files only** (training code is not included)

* Folder structure and input format follow **standard assumed values**
  * Example: weekday, rolling average, encoded categories, etc.

* Models are trained with a **default assumption of INR (Indian Rupees)**

* The system is **currency-independent**, meaning it works with any currency if data is consistent

* Future versions may include **separate trained models for different currencies**:
  * INR
  * USD
  * EUR
  * and more

---

## Training Data Note

This model is trained using a **custom CSV dataset of expense records** containing fields such as date, amount, and category. 

The dataset includes realistic financial transactions across multiple categories like food, travel, bills, entertainment, health, and shopping. The models were trained specifically on this structured data to learn spending patterns and behavior trends.

---

## Currency Assumption and Future Support

* The current model treats amounts as **numerical values**

* By default, usage can be considered as **INR**

* Risk thresholds (example: amount > 500 → HIGH risk) are based on this dataset

* These thresholds may need adjustment depending on currency or region

---

### Future Updates

* Multi-currency trained models (USD, EUR, etc.)
* Better scaling and normalization
* Improved accuracy and optimization
* Expanded dataset support

---

## Note to Users

You can directly use these `.pkl` models in your own applications without retraining.

More advanced versions and improvements will be released over time.

---

## Models Used and Training Process

### Models Used

* Random Forest Regressor → Spending prediction  
* Gradient Boosting Regressor → Improved prediction accuracy  
* Logistic Regression → Risk classification  
* Decision Tree Classifier → Baseline comparison  
* Random Forest Classifier → Improved classification  
* Support Vector Machine (SVM) → Risk comparison  
* MLP Classifier → NLP-based category prediction  
* K-Means Clustering → Behavior grouping  

---

### Training Process (Step by Step)

* Load CSV dataset (date, amount, category)
* Clean dataset (remove duplicates, handle missing values)
* Feature engineering:
  * Extract weekday, month, etc.
  * Create rolling average
* Encode categorical data (one-hot encoding)
* Train regression models:
  * Random Forest
  * Gradient Boosting
* Evaluate models using MAE and select best model
* Create risk labels:
  * amount > 500 → HIGH risk
* Train classification models and compare using recall
* Train NLP model:
  * TF-IDF vectorization
  * MLP classifier
* Apply K-Means clustering:
  * Group based on spending patterns

---

### Model Saving

* All models are saved using `joblib`
* Stored as reusable `.pkl` files
* Includes:
  * Prediction model
  * Risk model
  * NLP model + vectorizer
  * Clustering model
  * Feature structure

---

## What This Model Does

This system provides:

* Spending prediction  
* Risk detection (HIGH / LOW)  
* Expense category classification  
* Behavior clustering  
* Financial decision suggestions  

---

## About the `.pkl` Files

All `.pkl` files are **pre-trained machine learning models**.

### Files Included:

* `spending_model.pkl` → Predict spending  
* `risk_model.pkl` → Risk classification  
* `nlp_model.pkl` → Category prediction  
* `tfidf.pkl` → Text vectorizer  
* `kmeans.pkl` → Clustering  
* `feature_columns.pkl` → Input structure  

---

## How to Use

### 1. Install Requirements

```bash
pip install pandas numpy scikit-learn joblib
```

### 2. Load Models

```python
import joblib

spending_model = joblib.load("spending_model.pkl")
risk_model = joblib.load("risk_model.pkl")
nlp_model = joblib.load("nlp_model.pkl")
vectorizer = joblib.load("tfidf.pkl")
kmeans = joblib.load("kmeans.pkl")
```

### 3. Example Input

```python
input_data = {
    "weekday": 2,
    "rolling_avg": 500
}
```

### 4. Predict

```python
prediction = spending_model.predict([list(input_data.values())])
print(prediction)
```

---

## System Features

* Multi-model AI system  
* Works on structured CSV data  
* Includes NLP capabilities  
* Behavioral clustering  
* Easy integration using `.pkl` files  

---

## Use Cases

* Personal finance apps  
* Budget tracking systems  
* Expense analytics tools  
* Academic ML projects  
* Financial dashboards  

---

## License

This project is licensed under the **MIT License**.

You are free to:

* Use  
* Modify  
* Distribute  
* Use commercially  

---

## ⚠️ Credit Requirement

If you use this project, models, or system in any form (personal, academic, or commercial), you **must provide credit**:

**Krishnamohan Yagneswaran**

---

## Future Improvements

* Web application interface  
* Mobile app integration  
* API deployment  
* Real-time analytics  
* Multi-currency trained models  

---

## Conclusion

This project demonstrates how multiple machine learning models can be combined into a single intelligent financial system. It is simple, scalable, and ready for real-world usage.

---

**Created by:**  
Krishnamohan Yagneswaran
