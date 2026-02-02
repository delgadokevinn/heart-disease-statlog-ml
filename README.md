# Heart Disease Statlog – EDA and Prediction

This project analyzes the Statlog Heart Disease dataset and builds a machine learning model to predict whether a patient has heart disease based on clinical features.

## Dataset

- Source: Statlog (Heart) dataset (UCI / Kaggle version).
- Samples: 271 patients.
- Features (subset):  
  - `age` – Age in years.  
  - `sex` – 1 = male, 0 = female.  
  - `cp` – Chest pain type (0–3).  
  - `trestbps` – Resting blood pressure (mm Hg).  
  - `chol` – Serum cholesterol (mg/dl).  
  - `thalach` – Maximum heart rate achieved.  
  - `exang` – Exercise‑induced angina (1/0).  
  - `oldpeak` – ST depression induced by exercise.  
  - `slope` – Slope of the peak exercise ST segment.  
  - `ca` – Number of major vessels (0–3).  
  - `thal` – Thalassemia test result.  
  - `target` – 0 = no heart disease, 1 = heart disease.

## Project structure

- `heart_disease_statlog.ipynb` – Jupyter notebook with:
  - Data loading and cleaning.
  - Exploratory data analysis (EDA) with plots:
    - Chest pain type vs heart disease (proportions).
    - Max heart rate vs heart disease.
    - ST depression (`oldpeak`) vs heart disease.
  - Random forest classifier to predict `target`.
  - Feature importance analysis.
  - Simple risk‑prediction function for new patients.

- `Heart_disease_statlog.csv` – Dataset used in the notebook.

## Model

- Algorithm: Random Forest classifier (`sklearn`).
- Train/test split: 80/20 with stratification on `target`.
- Test performance (approximate):
  - Accuracy: ~0.83
  - F1 (no disease, class 0): ~0.85
  - F1 (heart disease, class 1): ~0.82

Key predictive features include chest pain type (`cp`), thalassemia result (`thal`), number of major vessels (`ca`), ST depression (`oldpeak`), and maximum heart rate (`thalach`).

## How to run

```bash
# clone the repo
git clone https://github.com/<your-username>/heart-disease-statlog-ml.git
cd heart-disease-statlog-ml

# (optional) create a virtual environment, then install dependencies
pip install -r requirements.txt

# open the notebook
jupyter notebook heart_disease_statlog.ipynb
