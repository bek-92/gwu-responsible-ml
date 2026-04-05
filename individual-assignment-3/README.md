# Individual Assignment 3 — Algorithmic Bias Measurement

## Purpose
This notebook conducts a disparate impact audit of the COMPAS 
recidivism risk scoring tool using 6,172 defendants from Broward 
County, Florida.

## Tasks Completed
1. AIR and Marginal Effect by race and sex (manual + solas_disparity)
2. Intersectional subgroup analysis (race x sex)
3. FPR and FNR disparity by race with two-proportion z-test
4. Publication-quality grouped bar chart of FPR and FNR by race
5. 300-word compliance memo addressed to a hypothetical regulator

## Key Findings
- African-American defendants flagged at 1.74x the rate of Caucasians
- Black defendants face a false positive rate nearly double that of White defendants (0.423 vs 0.220)
- Worst intersectional subgroup: Hispanic/Female (AIR = 0.270)

## Libraries Used
- pandas, numpy, matplotlib, scipy
- statsmodels (proportions_ztest)
- solas-ai (solas_disparity)
