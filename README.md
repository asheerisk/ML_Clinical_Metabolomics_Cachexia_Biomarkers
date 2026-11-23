# Supervised Machine Learning Biomarker Discovery in Clinical Metabolomics (`Human Cachexia`)

## Overview
End-to-end supervised machine learning pipeline (`scikit-learn`) applied to targeted urinary metabolomics profiles (`human_cachexia.csv`, **77 patients**, **63 quantified metabolites**) to classify **Cancer Cachexia** vs. **Healthy Controls** and rank diagnostic metabolite biomarkers.

## Workflow & Key Results
1. **Leakage-Free Preprocessing (`pandas`, `scikit-learn`):**
   - Encoded clinical phenotypes (`0 = Control`, `1 = Cachexic`) and performed a stratified 80/20 train-test split.
   - Applied `StandardScaler` fit strictly on the training set before transforming held-out test samples.
2. **Model Training & Validation (`RandomForestClassifier`):**
   - Trained a 100-tree Random Forest classifier and verified generalizability using **5-Fold Stratified Cross-Validation** (`Mean CV Accuracy: 67.58%`, `Mean CV ROC-AUC: 0.756`).
   - Evaluated on the unseen 20% test cohort (`Test Accuracy: 62.50%`, `Test ROC-AUC: 0.733`).
3. **Biomarker Feature Importance:**
   - Ranked all 63 metabolites by Gini importance to pinpoint the primary metabolic drivers of muscle-wasting cachexia.

## Repository Structure
- `03_Clinical_Metabolomics_ML_Cachexia_Biomarkers.ipynb`
- `README.md`
- `results/figures/cachexia_ml_evaluation.png`
- `results/figures/cachexia_top10_biomarkers.png`
- `results/tables/cachexia_metabolite_feature_importance.csv`
