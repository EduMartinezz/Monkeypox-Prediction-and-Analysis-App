# Monkeypox-Prediction-and-Analysis-App
This project is an interactive web application for predicting Monkeypox infection and analyzing related data using machine learning models. This is an update from the initial project on monkeypox.

## Overview
This project is an **interactive web application for predicting Monkeypox infection and analyzing related data using machine learning models**. Built with Streamlit, it provides **exploratory data analysis (EDA)**, **model training, advanced analysis, and prediction capabilities**. The app is deployed using **Google Colab** and **Ngrok** for easy access via a **public URL.**
The app leverages a variety of **machine learning algorithms** (e.g., **Logistic Regression, XGBoost, ensemble methods**) and offers visualizations like **correlation heatmaps, ROC curves, and SHAP summaries** to interpret results. It supports both a pre-uploaded dataset (Monkeypox_Dataset.csv) and **user-uploaded datasets** for flexibility.

## Features
**Exploratory Data Analysis (EDA):**
- Dataset info, descriptive statistics, and missing value summaries.
- Visualizations: **MPOX result distribution, age distribution, correlation heatmap.**

**Model Training:**
- Trains **9 individual models (e.g., Logistic Regression, Decision Tree, XGBoost).**
- Trains **3 ensemble models (Voting, Bagging, Stacking).**
- Displays **accuracy scores, classification reports, and ROC curves.**
- **Model comparison table** and **bar plot.**

**Advanced Analysis:**
- **Hyperparameter tuning** with **Grid Search** and **Bayesian optimization.**
- **Cross-validation scores** and **confidence intervals.**
- **Feature importance (XGBoost), SHAP summaries, outlier detection, and partial dependence plots.**

**Prediction:**
- **Interactive input form** to predict **Monkeypox status** using the trained **XGBoost model.**

**Flexible Data Input:**
- Uses a default **Monkeypox_Dataset.csv** pre-uploaded in **Colab.**
- Allows users to **upload their own dataset** via the dashboard.

## Prerequisites
- **Google Colab Account**: For running the notebook and deploying the app.
- **Ngrok Account**: For creating a public URL (free tier works; requires an auth token).
- **Python 3.11**: The app is built and tested with this version (via Colab).
- **Dataset**: A CSV file with Monkeypox-related data.

**Installation**
- Clone the Repository
**Open in Google Colab**:
- Upload the monkeypox_app.ipynb (or equivalent .ipynb file) to Google Colab.
- Alternatively, copy-paste the notebook code into a new Colab notebook.

**Upload the Dataset**:
- Place Monkeypox_Dataset.csv in your local directory and upload it when prompted in Colab (Step 2 
  of the notebook).
- Or prepare a similar dataset for upload via the dashboard.

**Get Ngrok Auth Token**:
- Sign up at **ngrok.com**.
- Copy your **auth token** from the dashboard (e.g., 2tZ6mqHFZ9n2B4HsTOzAPVA3Jnw_6qB1RFncPLxV8kcYUxNcJ).

## Usage
1. **Run the Colab Notebook:**
   - Open the notebook in Google Colab.
   - Execute all cells sequentially:
      1. Install libraries.
      2. Upload Monkeypox_Dataset.csv.
      3. Write app.py.
      4. Set up Ngrok and run Streamlit.
      5. Check logs.
      - After Step 4, you’ll get a public URL (e.g., https://<random-id>.ngrok-free.app).

2. **Access the Dashboard:**
    - Open the Ngrok URL in your browser.
    - You’ll see the Streamlit app interface.

3. **Interact with the Dashboard:**
    - **EDA**: Explore dataset statistics and visualizations.
    - **Model Training**: Select this to train models and view performance metrics.
    - **Advanced Analysis**: Analyze the trained model (requires prior training).
    - **Prediction**: Input **patient data** to predict **Monkeypox status** (requires prior                training).
    -   Optionally, upload a custom dataset via the file uploader.

4. **Example Workflow**:
    - Navigate to **"Model Training"** to train models.
    - Switch to **"Advanced Analysis"** for deeper insights.
    - Go to **"Prediction"**, enter feature values (e.g., **Age, Rectal Pain**), and click 
    **"Predict"**.

## Dataset Requirements
The app expects a CSV file with the following columns (case-insensitive):
- **MPOX PCR Result**: Target variable (Positive/Negative).
- **Feature Columns**:
  - Rectal Pain, Sore Throat, Penile Oedema, Oral Lesions, Solitary Lesion, Swollen Tonsils, HIV 
    Infection, Health Insurance, Sexually Transmitted Infection: Binary (e.g., YES/No, 1/0).
- **Age**: Numeric (e.g., 0-120).
  
- **Optional Columns** (dropped during preprocessing):
  -  Month of Birth, White blood cells count, Red blood cells count, Home ownership, Systemic 
     Illness, Test ID.

**Notes:**
- Missing values in binary columns are filled with 0 (assumed "No").
- Age values outside 0-120 or invalid (e.g., -23) are replaced with the median.
- Custom datasets must match this structure for full compatibility.

## Project Structure
<your-repo-name>/
│
├── monkeypox_app.ipynb    # **Colab notebook** with full code
├── Monkeypox_Dataset.csv  # **Default dataset** (optional; upload in **Colab**)
├── README.md              # This file
└── requirements.txt       # List of **Python dependencies** (optional)

## Dependencies
The app uses the following Python libraries (installed via Colab):
- streamlit: Web app framework.
- pandas, numpy: Data manipulation.
- matplotlib, seaborn: Visualization.
- scikit-learn: Machine learning models and metrics.
- xgboost: XGBoost model.
- shap: Model interpretability.
- scikit-optimize: Bayesian optimization.
- pyngrok: Ngrok integration.
See the notebook’s first cell for the full **pip install** command.

## Deployment
The app is deployed using Google Colab and Ngrok:
1. Colab: Runs the Python environment and Streamlit server.
2. Ngrok: Creates a public tunnel to the local Streamlit server (port 8501).
    - Replace the Ngrok auth token in the notebook with your own.

**Steps:**
- Run the notebook cells.
- Get the Ngrok URL from the output.
- Access the URL in your browser.
**Note**: The deployment lasts as long as the Colab runtime is active (typically 12 hours max, or 
  until disconnected).

## Limitations
- **Runtime**: Colab sessions reset after ~12 hours, requiring re-running the notebook.
- **Dataset Dependency**: Assumes a specific dataset structure; custom datasets may need 
    preprocessing adjustments.
- **Ngrok**: Free tier URLs change with each run; paid plans offer static URLs.
- **Scalability**: Designed for small-to-medium datasets due to Colab’s resource limits.

## Future Improvements
- Add support for more dataset formats (e.g., JSON, Excel).
- Implement real-time model retraining with uploaded data.
- Deploy on a persistent server (e.g., Heroku, AWS) instead of Colab.
- Enhance error handling for incompatible datasets.
- Add export options for model results and visualizations.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a branch (git checkout -b feature/<your-feature>).
3. Commit changes (git commit -m "Add <your-feature>").
4. Push to the branch (git push origin feature/<your-feature>).
5. Open a pull request.

Please include tests and update the README if needed.

## License
This project is licensed under the .

## Acknowledgments
- Streamlit: For the intuitive web app framework.
- xAI: Inspiration from Grok (AI assistant context).
- Ngrok: For easy tunneling to Colab.
- Scikit-learn & XGBoost: For robust ML tools.

**Contact**
For questions or feedback, reach out to:
Email: edumartinezbe@gmail.com
