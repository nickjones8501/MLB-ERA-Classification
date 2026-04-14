# MLB Good ERA vs Bad ERA Classification Model

## Overview
A Random Forest classification model that predicts whether an MLB team 
had a "Good" or "Bad" ERA in a given season (2010–2025), using team-level 
pitching statistics.

## Dataset
- MLB team pitching stats from 2010–2025
- Features: FIP, xFIP, K/9, BB/9, HR/9, BABIP, LOB%, GB%, WAR, and more
- Target: Good_ERA (1 = at or below median ERA of 4.049, 0 = above)

## Model
- Algorithm: Random Forest (400 estimators)
- Train/Test Split: 80/20
- **Accuracy: 88.5%**

## Key Findings
- Top predictors: LOB%, FIP, xFIP, BABIP
- FIP and xFIP are the strongest ERA-related predictors
- LOB% (strand rate) was surprisingly the #1 feature

## Files
- `notebooks/era_classification.ipynb` — full model code
- `outputs/` — all visualizations

## Requirements
```bash
pip install pandas numpy matplotlib scikit-learn
```
