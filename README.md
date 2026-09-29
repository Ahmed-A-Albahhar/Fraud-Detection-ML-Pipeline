# Fraud Detection & Anomaly Recognition ML Pipeline

## 📌 Project Overview
This project focuses on identifying fraudulent credit card transactions through advanced machine learning techniques. Leveraging a Kaggle dataset of over 1.29 million transactions and 23 features, the objective was to build and evaluate predictive models capable of distinguishing fraudulent activities from legitimate ones to enhance financial system security.

## 💡 Business Impact & Key Takeaways
* **High-Precision Detection:** Engineered an XGBoost classification model that achieved over 99.7% accuracy in identifying fraudulent transactions, enabling reliable real-time transaction monitoring.
* **Fraud Driver Identification:** Permutation importance analysis revealed that transaction amount and merchant category are the primary predictors of fraud, allowing businesses to set targeted transaction flags.
* **Demographic Risk Profiling:** Identified that middle-aged individuals (ages 30 to 65) are the most susceptible to fraudulent transactions, providing actionable intelligence for targeted customer security alerts.

## ⚙️ Data Preprocessing & Feature Engineering
To prepare the 1.29 million rows for modeling, extensive data cleaning and engineering pipelines were developed:
* **Missing Data Handling:** Isolated 195,973 missing values in the `merch_zipcode` column into a dedicated "Missing" category to preserve data integrity without introducing imputation bias.
* **Feature Engineering:** Calculated geographical distance between transactions and merchants using latitude/longitude data, classifying them into distinct distance categories (e.g., very close, far).
* **Data Standardization:** Corrected data entry errors in credit card numbers by padding strings to match standard 15-digit (Mastercard) and 16-digit (Visa) formats.
* **Encoding & Scaling:** Applied frequency-based label encoding for categorical variables (merchant, category, gender) and standard scaling for skewed numerical features like transaction amount and city population.

## 🧠 Model Building & Evaluation
An array of base learners was trained, including K-Nearest Neighbors, Decision Trees, Gaussian Naive Bayes, Random Forest, Linear SVC, and Logistic Regression.

* **Winning Model:** The **XGBoost Classifier** outperformed all other models with an accuracy of 0.9972.
* **Feature Importance:** Built-in model metrics and permutation importance confirmed that `amt` (Transaction Amount) and `category_encoded` overwhelmingly influenced the model's predictive power.

## 🚀 Strategic Recommendations
* Integrate the XGBoost model into financial authorization flows for real-time transaction monitoring.
* Implement continuous model retraining pipelines to adapt to evolving fraud patterns.
