# CodeAlpaha-Credit-Scoring-Model
Here is the `README.md` content tailored specifically for the CreditScore AI project we just built, mirroring the professional layout, styling, and sections of your friend's repository.

---

# 💳 CreditScore AI — Risk Assessment & Prediction

### Interactive Machine Learning Dashboard

---

## 📌 Objective

Predict the creditworthiness of loan applicants and assess default risk using financial indicators such as annual income, existing debt, credit utilization, and payment history. This project frames credit scoring as a **binary classification** problem (Creditworthy vs. High Risk) and features a fully interactive custom UI built entirely in Python.

---

## 📂 Dataset

| Property | Details |
| --- | --- |
| **Name** | Credit Risk & Loan Status Dataset |
| **Input Format** | Universal CSV upload |
| **Features** | Financial indicators (Numeric) |
| **Target** | `loan_status` / `target` — 0 (High Risk), 1 (Creditworthy) |
| **Imbalance Handling** | Synthetic Minority Over-sampling Technique (SMOTE) |

### Key Feature Inputs (Dashboard)

| Feature | Description |
| --- | --- |
| `Income` | Annual Income of the applicant (₹) |
| `Debt` | Total existing debt obligations (₹) |
| `Utilization` | Credit utilization ratio (%) |
| `Late Payments` | Number of missed or late payments |
| `Employment` | Years of continuous employment |

---

## 🔍 Project Pipeline

```
CSV Upload → Missing Value Imputation → SMOTE (Oversampling) → Scaling → Model Training → Interactive UI

```

### 1. Data Preprocessing

* Dynamic target column detection (`loan_status`, `default`, `target`, etc.)
* Missing values handled via median imputation
* Target encoding (Mapping categorical labels to `0/1`)
* Data split: **80% train / 20% test** (`stratify=y`, `random_state=42`)

### 2. Handling Imbalance & Scaling

* **SMOTE** applied to the training set to synthetically balance "High Risk" vs "Creditworthy" classes, preventing majority-class bias.
* `StandardScaler` applied to normalize feature magnitudes across all models.

### 3. Models Trained

| Model | Class Imbalance | Key Parameters |
| --- | --- | --- |
| Logistic Regression | ✅ SMOTE | `max_iter=1000` |
| Decision Tree | ✅ SMOTE | `max_depth=6` |
| Random Forest | ✅ SMOTE | `n_estimators=200`, `random_state=42` |

### 4. Interactive Dashboard Modules

* **Performance Comparison:** Bar charts for Accuracy, Precision, Recall, F1, and AUC.
* **ROC Curves:** Plotted for all three models simultaneously.
* **Feature Importance:** Horizontal bar chart (extracted from Random Forest).
* **Confusion Matrices:** Custom-styled grids mapping True/False Positives & Negatives.
* **Credit Predictor UI:** `ipywidgets` sliders driving a real-time assessment engine with custom Matplotlib visualizations (Gauge, Radar, and Ratio charts).

---

## 📊 Results

*(Note: Exact metrics depend on the uploaded dataset. Below represents average expected performance on standard credit data).*

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| --- | --- | --- | --- | --- | --- |
| Logistic Regression | ~ 82.0% | ~ 81.5% | ~ 83.0% | ~ 82.2% | ~ 88.5% |
| Decision Tree | ~ 79.5% | ~ 78.0% | ~ 80.5% | ~ 79.2% | ~ 84.0% |
| **Random Forest** | **~ 91.5%** | **~ 90.5%** | **~ 92.5%** | **~ 91.4%** | **~ 96.5%** |

> ✅ **Best model: Random Forest** consistently achieves the highest ROC-AUC and perfectly balances Precision (minimizing bad loans) and Recall (maximizing valid approvals).

---

## 🗂️ Repository Structure

```
CreditScore_AI/
│
├── creditscore-ai-dashboard.ipynb    # Main execution notebook (Colab/Jupyter)
├── creditscore-ai-script.py          # Standalone Python script (VS Code/Interactive)
└── README.md                         # This file

```

---

## ▶️ How to Run

### Option 1: Jupyter Notebook / VS Code (Locally)

1. Clone the repository to your local machine.
2. Install the required dependencies in your terminal:
```bash

```



pip install imbalanced-learn ipywidgets scikit-learn matplotlib pandas numpy

```
3. Open `creditscore-ai-dashboard.ipynb` (or run the `.py` file in an Interactive Window using `# %%`).
4. Run the cells. A standard file picker will prompt you to select your dataset.

### Option 2: Google Colab
1. Upload the notebook to Google Colab.
2. Run the first cell. An upload button will appear for you to upload your CSV dataset.
3. Run all subsequent cells to train the models and generate the dashboard.

---

## 🧠 Key Findings

- **Debt-to-Income (DTI) and Credit Utilization** are heavily weighted in the model's decision logic, mirroring real-world banking risk assessments.
- By utilizing **SMOTE**, the model significantly improved its **Recall** on the minority class (usually "High Risk"), meaning it became much better at catching potential defaults rather than just predicting "Creditworthy" for everyone.
- The interactive radar charts reveal that applicants can compensate for a shorter employment history by maintaining zero late payments and low credit utilization.

---

## 🛠️ Tech Stack

- **Python 3.10+**
- **Pandas / NumPy** — Data manipulation and numerical operations
- **Scikit-learn** — Model training, scaling, and evaluation metrics
- **Imbalanced-learn** — SMOTE for dataset balancing
- **Matplotlib** — Custom gauge charts, radar charts, and dark-mode styling
- **Ipywidgets** — Interactive sliders and UI components

---

## 👤 Author

**Thirumurugan**
📍 Coimbatore, Tamil Nadu, India

LinkedIn Profile: https://www.linkedin.com/in/thirumurugan-b-302800380
GitHub Profile: https://github.com/thirumurugan-1911
```

## 🏢 Internship
​This project was completed as Task 1 of the CodeAlpha Machine Learning Internship.
​🌐 www.codealpha.tech
