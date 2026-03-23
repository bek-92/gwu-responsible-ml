# Individual Assignment 1 — Translating an R Machine Learning Workflow into Python

## Purpose of the Analysis
This notebook reproduces the ProPublica COMPAS Recidivism Risk Score analysis 
originally written in R, translated entirely into Python. The analysis performs 
exploratory data analysis (EDA), builds a logistic regression model, and conducts 
model diagnostics to examine racial bias in the COMPAS algorithm.

## Python Libraries Used
- `pandas` — data loading, filtering, preprocessing, and descriptive statistics
- `numpy` — exponential calculations for relative risk interpretation
- `matplotlib` — bar chart visualizations of decile score distributions
- `statsmodels` — logistic regression model

## Instructions for Reproducing the Results
1. Open `Lecture_01_alignment_Python_3.ipynb` in Google Colab or Jupyter
2. Run all cells from top to bottom in order
3. The dataset loads automatically from the ProPublica GitHub repository
4. No additional data downloads are required
