# Fraud Detection Streamlit App
## 1. Objective
The objective of this project is to build an fraud detection application that allows users to input transaction details and receive real-time fraud predictions through an interactive web interface.

## 2. What This Project Does
- This project builds and deploys a fraud detection system that takes transaction information as input and predicts whether a transaction is fraudulent.

- A machine learning model is trained using a scikit-learn Pipeline that combines data preprocessing and classification in a single workflow. Numerical features are standardized, and the categorical transaction type is encoded to make the data suitable for modeling.

- To address class imbalance in the dataset, the Logistic Regression model is trained with class weighting, ensuring that fraudulent transactions receive appropriate importance during learning.

- After training and evaluation, the complete preprocessing and modeling pipeline is saved and reused in a Streamlit web application. The web app allows users to input transaction details through an interactive interface and receive real-time fraud predictions.
- 

## 3. Dataset
The dataset used in this project is sourced from Kaggle: [Fraud Detection Dataset](https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset?resource=download) 


## 4. Streamlit Application
The deployment logic is implemented in `Streamlit_web_app.py`.

The application provides input fields for transaction attributes, including transaction type and account balance information.

User inputs are collected and converted into a pandas DataFrame that matches the feature structure used during training.  
The loaded pipeline is then used to generate a prediction for the input data.

The prediction result is displayed directly in the web interface:
- A warning message is shown if the transaction is predicted as fraudulent
- A success message is shown otherwise

<div align="center">
  <img
    src="https://github.com/user-attachments/assets/ea5ea478-1223-414b-9923-a9fc5191e866"
    width="466"
    height="578"
    alt="Streamlit App Screenshot"
  />
</div>



## 5. How to Run the Streamlit App
1. Install dependencies
```bash
pip install -r requirements.txt
```
2. Run the application by typing the following command in the terminal
```bash
streamlit run Streamlit_web_app.py
```

## 6. Limitations
- The model is trained on a publicly available dataset and may not generalize to real-world production systems.

- Only a limited set of transaction-level features is used.

- The project focuses on building a complete and reproducible pipeline rather than maximizing predictive performance through extensive model tuning.

## 7. Notes
The Streamlit application assumes that fraud_detection_pipeline.pkl is located in the same directory as Streamlit_web_app.py.
If the model file is moved to a different folder, the loading path in the Streamlit script must be updated accordingly.
