# Maternal Health Risk Prediction - ML for Social Good

**Course:** Machine Learning (MCA 521-4)
**Assignment:** Continuous Internal Assessment – III (CIA 3)

## 📌 Project Overview
This project is an end-to-end machine learning pipeline designed to predict maternal health risk levels (**low risk**, **mid risk**, or **high risk**) based on vital signs and age. The goal is to demonstrate how machine learning can serve as a decision-support and triage tool in under-resourced healthcare clinics to help prioritize patient care.

## 📊 Dataset Citation
The dataset used in this project is the **Maternal Health Risk Data Set**, containing health metrics from different hospitals and community clinics.
- **Source:** [UCI Machine Learning Repository / Kaggle - Maternal Health Risk Dataset]
- **Target Variable:** `RiskLevel` (Low, Mid, High)
- **Features:** Age, Systolic BP, Diastolic BP, Blood Sugar (BS), Body Temperature, and Heart Rate.

> **Note:** The dataset does not contain personally identifiable information (PII) and complies with data privacy guidelines.

## 🚀 Execution & Reproducibility Instructions
To run this project and reproduce the results, please follow these steps:

### Prerequisites
Make sure you have Python installed along with the following libraries:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn lime
```

### Running the Notebook
1. Clone this repository or download the project files.
2. Ensure that the `Maternal Health Risk Data Set.csv` file is in the exact same directory as the notebook.
3. Open **`CIA 3_Student_Version.ipynb`** using Jupyter Notebook, JupyterLab, or VS Code.
4. Run the cells sequentially from top to bottom.
5. **Random Seed:** The random state `42` is used across all train/test splits, cross-validation, and models to ensure the results are 100% reproducible.

## 🧠 Models & Performance
The project compares a simple baseline model with advanced ensemble techniques:
1. **Logistic Regression (Baseline)**
2. **Random Forest (Bagging Ensemble)** - *Best Performing Model*
3. **AdaBoost (Boosting Ensemble)**
4. **Soft Voting Ensemble**

**Final Untouched Test-Set Results:**
The **Random Forest** model outperformed the baseline, achieving the best overall generalisation on unseen data:
- **Macro-F1 Score:** 0.617
- **ROC-AUC:** 0.803

## 🔍 Model Explainability
To ensure the AI is not a "black box," two explainability techniques were used:
- **Global Explainability (Permutation Importance):** Revealed that Blood Sugar (`BS`) and Blood Pressure features are the strongest overall predictors of maternal health risk across the dataset.
- **Local Explainability (LIME):** Used to explain individual patient predictions in real-time, helping clinicians understand *why* a specific patient was flagged as high-risk (e.g., heavily influenced by elevated blood sugar).

## ⚖️ Ethics, Fairness, and Limitations
- **Intended Use:** This model is designed strictly as a **decision-support and triage tool**. It must NEVER replace a qualified healthcare professional's diagnosis or treatment plan.
- **False Negatives:** Predicting a high-risk patient as low-risk could delay urgent care. The model's thresholds would need strict clinician oversight in a real-world setting.
- **Fairness:** Subgroup analysis indicated that the model struggles slightly more with teenage patients compared to older age brackets, highlighting the need for more diverse and balanced data.
- **Deployment Limitations:** The dataset is relatively small and lacks geographic/demographic diversity. Any real-world deployment would require rigorous external validation, secure HIPAA-compliant data storage, and constant human-in-the-loop oversight.

## 🎥 Pitch & Demo Video
[Link to the 3-minute Pitch and Demo Video] *(Insert your video link here)*
