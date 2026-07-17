# Predictive Maintenance using CMAPSS Turbofan Engine Dataset

An end-to-end machine learning pipeline for **predictive maintenance of aircraft engines** using NASA's CMAPSS turbofan degradation dataset. The project combines **unsupervised learning**, **classification**, and **regression** to estimate engine degradation stages, predict remaining time until the next degradation stage, and generate maintenance risk scores.

---

## Features

- Engine degradation stage discovery using clustering
- Comparison between K-Means and Agglomerative Clustering
- Multi-class degradation stage prediction
- Remaining time prediction using regression models
- Risk score calculation for maintenance prioritization
- Automatic maintenance alerts
- PCA visualization of degradation stages
- Risk score trend visualization

---

## Machine Learning Pipeline

```
CMAPSS Dataset
       │
       ▼
Data Preprocessing
       │
       ▼
K-Means & Agglomerative Clustering
       │
       ▼
Best Clustering Selection
(Silhouette Score)
       │
       ▼
Degradation Stage Labels
       │
       ├──────────────► Classification
       │                (XGBoost vs Logistic Regression)
       │
       └──────────────► Time Prediction
                         (Random Forest vs Gradient Boosting)
       │
       ▼
Risk Score Generation
       │
       ▼
Maintenance Alerts
```

---

## Models Used

### Unsupervised Learning
- K-Means Clustering
- Agglomerative Clustering

Model selection based on **Silhouette Score**.

---

### Classification Models

- XGBoost Classifier
- Logistic Regression

Used to predict engine degradation stages.

Evaluation metrics:
- Accuracy
- Classification Report
- Confusion Matrix

---

### Regression Models

- Random Forest Regressor
- Gradient Boosting Regressor

Used to estimate the remaining time before the next degradation stage.

Evaluation metrics:
- RMSE
- MAE
- R² Score

---

## Risk Score Formula

The maintenance risk score is calculated as:

```
Risk Score =
Failure Probability
----------------------------
Remaining Time + ε
```

The score is normalized between **0 and 1** for easier interpretation.

Higher score ⇒ Higher maintenance priority.

---

## Visualizations

The notebook generates:

- PCA visualization of degradation stages
- Confusion matrix
- Risk score vs time
- Final risk score for each engine
- Maintenance alert threshold

---

## Dataset

This project uses the **NASA CMAPSS Turbofan Engine Degradation Simulation Dataset**.

Dataset files used:

- FD001
- FD002
- FD003
- FD004

Each record contains:

- Engine Unit ID
- Cycle Number (Time)
- Operational Settings
- 21 Sensor Measurements

---

## Project Structure

```
.
├── code.ipynb
├── train_FD001.txt
├── train_FD002.txt
├── train_FD003.txt
├── train_FD004.txt
├── test_FD001.txt
├── test_FD002.txt
├── test_FD003.txt
├── test_FD004.txt
└── README.md
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)
- Matplotlib
- Seaborn

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/predictive-maintenance.git

cd predictive-maintenance
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Required Libraries

```text
numpy
pandas
scikit-learn
xgboost
imbalanced-learn
matplotlib
seaborn
```

---

## How to Run

1. Download the NASA CMAPSS dataset.
2. Update the dataset paths inside the notebook.
3. Open the notebook:

```bash
jupyter notebook code.ipynb
```

4. Execute all cells.

---

## Outputs

The pipeline produces:

- Predicted degradation stage
- Remaining time estimation
- Maintenance risk score
- Engine maintenance alerts
- Performance metrics
- PCA visualization
- Risk trend plots

---

## Future Improvements

- Deep learning based Remaining Useful Life (RUL) prediction using LSTM/GRU
- Transformer-based time-series models
- Explainable AI using SHAP
- Real-time streaming sensor integration
- Dashboard deployment using Streamlit
- Hyperparameter optimization using Optuna

---

## Results

The notebook compares:

- K-Means vs Agglomerative Clustering
- XGBoost vs Logistic Regression
- Random Forest vs Gradient Boosting

The best-performing models are automatically selected based on evaluation metrics and used for maintenance risk prediction.

---

## License

This project is intended for educational and research purposes.
