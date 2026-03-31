# Expense AI Intelligence System

**Author:** Krishnamohan Yagneswaran

---

## Overview

This project is a machine learning system that analyzes expense data and provides useful financial insights. It combines multiple models to predict spending, detect risk, classify transactions, and understand user behavior.

The system is designed to work with real-world expense data and help users make better financial decisions.

---

## Training Data Note

This model is trained using a **custom CSV dataset of expense records** containing fields such as date, amount, and category. 

The dataset includes realistic financial transactions across multiple categories like food, travel, bills, entertainment, health, and shopping. The models were trained specifically on this structured data to learn spending patterns and behavior trends.

---
## Currency Assumption and Future Support

* The current model is trained on expense data where amounts are treated as **generic numerical values**

* For practical usage, this implementation can be considered as **INR (Indian Rupees)** by default

* The system is **currency-independent**, meaning it can work with any currency if the data is consistent

* Risk thresholds (such as amount > 500) are based on the current dataset and may need adjustment depending on the currency used

---

### Future Updates

* Support for multiple currencies (USD, EUR, etc.) will be added in future versions
* Improved scaling and normalization will be introduced for better global usage
* Updated models will be released with enhanced accuracy and features

---

### Note to Users

You can use these `.pkl` models in your own applications and projects.
More advanced versions and improvements will be released over time.

If you are interested in updates and new models, follow me on Hugging Face:

**Krishnamohan Yagneswaran**


## Models Used and Training Process

### Models Used

* Random Forest Regressor → for spending prediction
* Gradient Boosting Regressor → for improved prediction accuracy
* Logistic Regression → for risk classification
* Decision Tree Classifier → for comparison
* Random Forest Classifier → for better classification performance
* Support Vector Machine (SVM) → for risk prediction comparison
* MLP Classifier → for NLP-based category prediction
* K-Means Clustering → for grouping spending behavior

---

### Training Process (Step by Step)

* Load CSV dataset containing date, amount, and category

* Remove duplicate records and handle missing values

* Convert date into useful features (day, month, weekday)

* Create rolling average feature for spending trends

* Convert category column into numerical format (one-hot encoding)

* Split dataset into training and testing sets

* Train regression models:

  * Random Forest
  * Gradient Boosting

* Evaluate using MAE and select best model

* Create risk labels (amount > 500 → HIGH risk)

* Train multiple classification models

* Compare using recall score and select best model

* Train NLP model:

  * Convert text using TF-IDF
  * Train MLP classifier for category prediction

* Apply K-Means clustering:

  * Group data based on amount and weekday

---

### Model Saving

* All trained models are saved using `joblib`

* Saved as `.pkl` files for reuse without retraining

* Files include:

  * Prediction model
  * Risk model
  * NLP model and vectorizer
  * Clustering model
  * Feature structure

* These `.pkl` files act as the final packaged AI system


## What This Model Does

This system provides the following outputs:

* Predicts how much money you may spend
* Identifies if a transaction is high risk or low risk
* Classifies the type of expense (food, travel, bills, etc.)
* Groups spending behavior into clusters
* Provides a simple financial decision suggestion

---

## About the `.pkl` Files

All the `.pkl` files in this repository are **trained machine learning models and components**. These files are saved using `joblib` and allow the system to be reused without retraining.

### Files Explanation:

* `spending_model.pkl`
  → Predicts future spending amount

* `risk_model.pkl`
  → Classifies whether spending is HIGH or LOW risk

* `nlp_model.pkl`
  → Predicts category from text input

* `tfidf.pkl`
  → Converts text into numerical format for NLP

* `kmeans.pkl`
  → Groups spending behavior into clusters

* `feature_columns.pkl`
  → Stores the correct input structure used during training

---

## How to Use

### 1. Install Required Libraries

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

* Uses multiple machine learning models together
* Works with structured CSV expense data
* Includes NLP for text-based classification
* Uses clustering for behavior analysis
* Provides decision-making suggestions

---

## Use Cases

* Personal finance tracking
* Budget planning
* Expense monitoring applications
* Financial analytics systems
* Academic and learning projects

---

## License

This project is licensed under the **MIT License**.

You are free to:

* Use
* Modify
* Distribute
* Use commercially

As long as the original license and author credit are included.

---

## Credits

If you use this project in your work, research, application, or product, it would be appreciated if you provide credit:

**Krishnamohan Yagneswaran**

This helps support further development and recognition of the project.

---

## Future Improvements

* Web application interface
* Mobile application integration
* API deployment
* Real-time analytics

---

## Conclusion

This project demonstrates how multiple machine learning techniques can be combined into a single intelligent system. It is simple, practical, and scalable for real-world applications.

---

**Created by:**
Krishnamohan Yagneswaran
