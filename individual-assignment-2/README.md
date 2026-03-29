# Individual Assignment 2 — Explainability and Interpretability

## Purpose of the Analysis
This notebook builds on the COMPAS Recidivism Risk Score analysis from Lecture 01. 
It applies three post-hoc explainability methods — SHAP, LIME, and DiCE 
Counterfactuals — to a Gradient-Boosted Tree model trained on the Broward County 
COMPAS dataset. The goal is to diagnose model behaviour, detect potential bias, 
and evaluate whether the model provides meaningful recourse to defendants.

## Python Libraries Used
- `pandas` and `numpy` — data manipulation
- `scikit-learn` — model training, preprocessing, train/test split
- `shap` — SHAP values and beeswarm/waterfall plots
- `lime` — Local Interpretable Model-agnostic Explanations
- `dice-ml` — DiCE counterfactual explanations
- `matplotlib` — visualizations
- `statsmodels` — logistic regression for racial bias analysis

## Instructions for Reproducing the Results
1. Open `Lecture_02_alignment.ipynb` in Google Colab or Jupyter Notebook
2. Run all cells from top to bottom in order
3. The notebook will automatically install `shap`, `lime`, and `dice-ml` 
   via the `!pip install` cells
4. All outputs, plots, and counterfactuals will be reproduced automatically
5. An internet connection is required to load the COMPAS dataset from GitHub
