# Individual Assignment 5: Security and Abuse Pathways on COMPAS

## Overview

This repository folder contains my submission for Individual Homework 05 in Responsible Machine Learning. The assignment extends the Lecture 05 security pipeline using the ProPublica COMPAS dataset and evaluates three applied attack settings:

1. PGD evasion audit
2. Label-flip poisoning with fairness monitoring
3. Membership inference depth

The analysis compares Logistic Regression (LR) and Gradient Boosted Tree (GBT) models using performance, fairness, robustness, and privacy metrics.

## Files

| File | Description |
|---|---|
| `Lecture_05_assignment_Bek.ipynb` | Main Colab/Jupyter notebook with code, outputs, charts, and markdown interpretation |
| `Report.docx` | Two-page written report summarizing methods, key findings, and mitigation plan |
| `README.md` | This file |

## Main Findings

### Baseline

The clean Logistic Regression model had a Test AUC of 0.735, while the Gradient Boosted Tree model had a Test AUC of 0.718. The clean fairness baseline showed higher false-positive rates for African-American defendants than for Caucasian defendants in both models.

### Part A: PGD Evasion

The PGD-style evasion attack affected Logistic Regression much more strongly than Gradient Boosted Tree. As epsilon increased, LR false-positive rates rose sharply for both racial groups. At the strongest perturbation level, almost all truly low-risk individuals were classified as high-risk. GBT appeared more stable under this specific PGD approximation.

### Part B: Label-Flip Poisoning

The label-flip poisoning attack was the highest-risk finding. AUC stayed close to the clean baseline, but AIR remained outside the fairness band of [0.80, 1.25] and worsened under some poison rates. This means an AUC-only monitoring process would likely miss the attack.

A PSI-based feature drift monitor would also not detect the label-flip poisoning attack because the attack changes labels, not feature distributions.

### Part C: Membership Inference

Membership inference risk was low in this experiment. LR had MI AUC of 0.500 and GBT had MI AUC of 0.502, meaning the confidence-score attack performed close to random guessing. The L2 regularization experiment also showed MI AUC values near 0.50 across all tested C values.

## Mitigation Plan

The main proactive mitigation is label-integrity monitoring before retraining. This includes checking group-specific label distributions, target-class shifts, and data-source anomalies.

The main reactive mitigation is attack-triggered rollback and retraining. If AIR or FPR by race worsens after a suspicious data update, the model should be paused, the training batch should be investigated, and the model should be retrained using the last verified clean dataset.

## How to Run

Open `Lecture_05_assignment_Bek.ipynb` in Google Colab or Jupyter Notebook and run the cells from top to bottom. The notebook downloads the COMPAS dataset directly from the ProPublica GitHub source.
