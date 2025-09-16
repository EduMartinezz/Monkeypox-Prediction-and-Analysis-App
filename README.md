# 🦠 Monkeypox (Mpox) Predictor & Evaluator

A machine learning web app that predicts **Monkeypox PCR test results** based on clinical and demographic features.  
This project demonstrates a **full ML workflow**: data preprocessing, exploratory analysis, model training, evaluation, and deployment with Streamlit.  

---

## 📖 Project Overview
- Builds a predictive model for **Mpox PCR results (Positive/Negative)** using clinical + demographic features.  
- Includes a **Streamlit dashboard** for:
  - Interactive evaluation (metrics, ROC/PR curves, confusion matrix)  
  - Prediction on new uploaded CSVs  
  - Downloadable predictions for further use  
- Demonstrates **portfolio-ready data science skills**: preprocessing, feature engineering, ML modeling, deployment.  

---

## 📊 Dataset
- **Source**: `Monkeypox_Dataset.csv` (educational/demo dataset)  
- **Target column**: `MPOX PCR Result` (`Positive` / `Negative`)  

**Features:**
- **Numeric (14):**  
  `Encoded Systemic Illness, Rectal Pain, Sore Throat, Penile Oedema, Solitary Lesion, Swollen Tonsils, HIV Infection, Red blood cells count, White blood cells count, Home ownership, Age, Month of Birth, Health Insurance, Sexually Transmitted Infection`  
- **Categorical (2):**  
  `Oral Lesions, Systemic Illness`  

> **Note:** The pipeline automatically coerces text values (`"Twenty"`, `"Yes"`, `"No"`) into numeric equivalents. Missing values are imputed.

---

## 🚀 Features
- **Data Preprocessing**
  - Missing value imputation  
  - Word-to-number conversion (`"Twenty"` → `20`)  
  - Encoding of categorical variables with one-hot encoding  
  - Scaling of numeric variables  

- **Modeling**
  - Logistic Regression (balanced)  
  - Random Forest Classifier (for stronger performance)  
  - Cross-validation to assess robustness  

- **Evaluation Dashboard**
  - Accuracy, F1, ROC AUC  
  - Confusion Matrix  
  - ROC Curve & Precision–Recall Curve  
  - Suggested **optimal decision threshold** for best F1 score  
  - Top feature importance plot  

- **Prediction Dashboard**
  - Upload CSVs with the same schema  
  - Get predicted labels + probability of being positive  
  - Download results as `predictions.csv`  

---

### 🛠️ Tech Stack
- **Language:** Python  
- **Libraries:** pandas, numpy, scikit-learn, seaborn, matplotlib  
- **Deployment:** Streamlit + ngrok (for Colab public URL)  
- **Environment:** Google Colab  

---

### 📈 Example Results
Using the demo dataset:  

| Metric        | Value |
|---------------|-------|
| Accuracy      | 0.81  |
| F1 Score      | 0.84  |
| ROC AUC       | 0.89  |
| Optimal Threshold | ~0.29 (F1 ≈ 0.80+) |

> These results may vary depending on retraining and model choice (Logistic Regression vs Random Forest).  

---

### ▶️ Quickstart (Colab / Local)
1. Clone this repo or upload it to Colab  
   ```bash
   git clone https://github.com/your-username/mpox-predictor.git
   cd mpox-predictor


### 2. Install requirements
      pip install -r requirements.txt


### 3. Train (or retrain) and export model
       import joblib
       joblib.dump(pipe, "mpox_pipeline.joblib")

### 4. Run the Streamlit app
      Run the Streamlit app

### 5. (Optional, in Colab) Expose public URL with ngrok
      from pyngrok import ngrok
      ngrok.set_auth_token("YOUR_TOKEN")
      public_url = ngrok.connect(8501)
      public_url

## 📷 Screenshots
## Feature Info & Evaluation
## Prediction Output

### 📂 Project Structure
├── app.py                 # Streamlit dashboard
├── notebooks/             # Data cleaning, EDA, training notebook
├── mpox_pipeline.joblib   # Trained model (exported pipeline)
├── Monkeypox_Dataset.csv  # Example dataset
├── requirements.txt       # Dependencies
└── README.md              # Project documentation

### 🎯 Portfolio Value

    - Shows ability to design and deploy ML applications

    - Demonstrates practical problem-solving (handling messy real-world data like "Twenty" in     
      numeric fields)
