# Individual Assignment 4 — Python Coding Audit

## Purpose
This notebook evaluates the robustness, generalization, and fairness of a logistic regression model using the COMPAS dataset.

## Tasks Completed

### Part A: Distribution Drift
- PSI for numeric features (age, priors_count, decile_score)
- KS test for distribution comparison
- MMD in feature space
- Train vs test score distribution visualization

### Part B: Generalization
- Train vs test accuracy comparison
- AUC and log loss evaluation
- Generalization gap analysis

### Part C: Spurious-Correlation Probe
- Counterfactual analysis by modifying age
- Measurement of prediction sensitivity

### Part D: Robustness
- Stress test by increasing priors_count
- Evaluation of performance stability
- Analysis of prediction changes
- ICE curves and sensitivity summary

### Part E: Slice-Based Evaluation
- Performance comparison across race, sex, and age groups
- Identification of subgroup disparities

## Key Takeaways
- The model shows minimal distribution drift between train and test sets.
- Generalization performance is stable, with small gaps across metrics.
- Sensitivity tests reveal that predictions can change under input perturbations.
- Slice-based evaluation highlights differences across demographic groups, showing that aggregate metrics alone are not sufficient.
