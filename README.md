# 🏨 Hotel Reservation Cancellation Prediction

## Machine Learning Classification Project

Predicting hotel reservation cancellations using guest, booking, stay, timing, pricing, and historical booking features.

---

## 📌 Project Overview

Hotel reservation cancellations can create unsold rooms, revenue uncertainty, and operational challenges.

This project develops a machine learning classification pipeline to predict whether a hotel reservation will be cancelled.

The analysis combines exploratory data analysis, feature engineering, multiple classification algorithms, hyperparameter tuning, model evaluation, and SHAP explainability.

The project includes:

- Exploratory Data Analysis
- Data preprocessing
- Feature engineering
- Categorical encoding
- Model comparison
- Hyperparameter tuning
- Stratified train-test split
- Classification evaluation
- SHAP model explainability
- Business recommendations

---

## 🎯 Objective

Build a machine learning model that can identify reservations with a higher probability of cancellation.

The goal is to help hotels make better decisions around:

- Revenue management
- Overbooking strategies
- Guest retention
- Confirmation campaigns
- Deposit and pricing policies

---

## 📊 Dataset

The dataset contains **36,275 hotel bookings** and **17 features**.

The target variable is:

**booking_status**

which indicates whether the reservation was cancelled.

The dataset contains information about:

- Number of adults
- Number of children
- Weekend nights
- Week nights
- Meal type
- Car parking requirements
- Lead time
- Arrival year
- Arrival month
- Arrival date
- Market segment
- Repeated guest status
- Previous cancellations
- Previous completed bookings
- Average room price
- Special requests
- Booking status

The data dictionary provides definitions for the major dataset fields. :contentReference[oaicite:0]{index=0}

---

## 🔍 Exploratory Data Analysis

The analysis investigated the major factors associated with hotel reservation cancellations.

### Key Findings

- Overall cancellation rate: **32.8%**
- Average lead time for cancelled bookings: **139 days**
- Online market segment cancellation rate: **36.5%**
- Repeat-guest cancellation rate: **1.7%**

Cancellation probability increased substantially with longer lead times, rising from **8.9% for bookings made 0–7 days before arrival to 73.9% for bookings made 180+ days in advance**.

Online bookings showed higher cancellation rates than corporate bookings, while repeat guests demonstrated substantially lower cancellation behavior. :contentReference[oaicite:1]{index=1}

---

## 🛠️ Feature Engineering

Several features were engineered to capture booking behavior and reservation characteristics.

### Engineered Features

- `total_nights`
- `total_guests`
- `has_previous_cancellation`
- `is_high_lead_time`
- `price_per_guest`

These features combine existing booking attributes to provide additional signals for cancellation prediction. :contentReference[oaicite:2]{index=2}

---

## 🧹 Data Preprocessing

The preprocessing workflow included:

- Removing `Booking_ID` because it is a unique identifier without predictive value
- Checking for missing values
- Reviewing feature distributions
- One-hot encoding categorical variables
- Standard scaling where required for Logistic Regression
- Stratified 80/20 train-test split

The dataset contained no missing values according to the project analysis. :contentReference[oaicite:3]{index=3}

---

## 🤖 Models Compared

Five classification algorithms were evaluated:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. LightGBM
5. XGBoost

Random Forest was further optimized using **GridSearchCV with 3-fold cross-validation**. :contentReference[oaicite:4]{index=4}

---

## 📈 Model Performance

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| **Random Forest (Tuned)** | **90.5%** | **88.7%** | **81.2%** | **84.8%** | **0.957** |
| XGBoost | 89.9% | 87.3% | 80.9% | 84.0% | 0.955 |
| LightGBM | 89.6% | 86.6% | 80.7% | 83.5% | 0.954 |
| Decision Tree | 87.9% | 83.3% | 78.9% | 81.0% | 0.933 |
| Logistic Regression | 81.2% | 74.9% | 64.0% | 69.1% | 0.871 |

The metrics were calculated on the held-out 20% test set containing 7,255 bookings. Random Forest achieved the strongest performance across the reported evaluation metrics. :contentReference[oaicite:5]{index=5}

---

## 🏆 Final Model

### Random Forest (Tuned)

The tuned Random Forest model was selected as the final model.

Performance:

- **Accuracy:** 90.5%
- **Precision:** 88.7%
- **Recall:** 81.2%
- **F1 Score:** 84.8%
- **ROC-AUC:** 0.957

The model was selected because it achieved the strongest results across the reported evaluation metrics rather than relying on a single metric. :contentReference[oaicite:6]{index=6}

---

## 🧠 SHAP Explainability

SHAP was used to understand why the model makes cancellation predictions.

The analysis identified the following major drivers:

1. **Lead Time**
2. **Average Price per Room**
3. **Special Requests**
4. **Price per Guest**
5. **Arrival Date / Month**
6. **Market Segment**

Lead time was identified as the strongest predictor, while special requests showed a protective relationship with cancellation risk. :contentReference[oaicite:7]{index=7}

---

## 💡 Business Insights

The model and analysis suggest several practical applications.

### High-Risk Reservations

Reservations with very long lead times and lower engagement signals can be flagged for additional attention.

### Online Market Segment

Online bookings showed a **36.5% cancellation rate**, compared with **10.9% for Corporate bookings**.

This suggests that online customers may benefit from additional confirmation or engagement strategies. :contentReference[oaicite:8]{index=8}

### Repeat Guests

Repeat guests had a cancellation rate of only **1.7%**, indicating strong loyalty and lower cancellation risk.

### Revenue Management

Predicted cancellation risk could potentially support:

- Proactive guest outreach
- Overbooking buffers
- Deposit policies
- Dynamic pricing decisions
- Retention campaigns

These are analytical recommendations from the project and would require further validation before real-world deployment. :contentReference[oaicite:9]{index=9}

---

## 📁 Repository Structure

Hotel-Reservation-Cancellation-Prediction/

├── data/
│   └── Hotel Reservations.csv
│
├── docs/
│   └── Hotel_Reservation_Cancellation_ShivKumar.pptx
│
├── notebooks/
│   └── Hotel_Reservation_Cancellation_Prediction.ipynb
│
├── .gitignore
├── README.md
├── requirements.txt
└── Description.docx

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- LightGBM
- XGBoost
- SHAP
- Jupyter Notebook

---

## 📌 Key Takeaways

- Hotel reservation cancellations represent a significant business challenge.
- **Lead time** is the strongest cancellation-related signal identified in the project.
- Repeat guests show substantially lower cancellation behavior.
- Online market-segment bookings have a higher cancellation rate.
- Feature engineering helps capture booking behavior more effectively.
- Tuned Random Forest achieved the strongest reported model performance.
- SHAP provides interpretable insights into the factors influencing cancellation predictions.

---

## ⚠️ Disclaimer

This project is an analytical and machine learning exercise based on historical hotel reservation data.

Model predictions should not be treated as guaranteed outcomes. Real-world deployment would require ongoing monitoring, validation on new data, appropriate threshold selection, and business-domain review.

---

## 👤 Author

**Shiv Kumar**

Data Analyst
