# ⚾ MLB ERA Classification Model

> Random Forest model classifying MLB team ERAs as Good or Bad using pitching stats from 2010–2025

---

## Overview

This project builds a binary classification model to predict whether an MLB team had a **Good** or **Bad** ERA in a given season. Using team-level pitching statistics from 2010–2025, a Random Forest classifier is trained to distinguish high-performing pitching staffs from low-performing ones.

A team is labeled **Good ERA (1)** if their ERA is at or below the dataset median of **4.049**, and **Bad ERA (0)** if above it.

---

## Model Performance

| Metric | Score |
|--------|-------|
| Accuracy | **88.5%** |
| Precision (Good ERA) | 0.91 |
| Recall (Good ERA) | 0.85 |
| F1-Score (avg) | 0.89 |

---

## Top Features

The most important predictors of a Good ERA, ranked by Random Forest feature importance:

1. **LOB%** — Left On Base percentage (strand rate)
2. **FIP** — Fielding Independent Pitching
3. **xFIP** — Expected FIP
4. **BABIP** — Batting Average on Balls In Play
5. **HR/9** — Home Runs per 9 innings

---

## Dataset

- **Source:** MLB team pitching statistics (2010–2025)
- **Size:** ~480 team-seasons
- **Features used:** `FIP`, `xFIP`, `K/9`, `BB/9`, `HR/9`, `BABIP`, `LOB%`, `GB%`, `HR/FB`, `WAR`, `WinPct`, `RunDiff`, and more

---

## Project Structure

```
MLB-ERA-Classification-DTSC3601/
├── README.md
├── notebooks/
│   └── MLB_ClassificationProj.ipynb     # Full model code
├── data/
│   └── Team_stats_2010-2025.csv     # Raw dataset
└── outputs/
    ├── confusion_matrix.png
    ├── feature_importances.png
    ├── era_distribution.png
    └── correlation_heatmap.png
```

---

## How to Run

### 1. Clone the repo
```bash
git clone https://github.com/nickjones8501/MLB-ERA-Classification-DTSC3601
cd MLB-ERA-Classification-DTSC3601
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib scikit-learn
```

### 3. Run the notebook
Open `notebooks/era_classification.ipynb` in Jupyter and run all cells.

> **Note:** Make sure `Team_stats_2010-2025.csv` is placed in the `data/` folder before running.

---

## Key Findings

- **LOB% and FIP** were the strongest predictors — suggesting that strand rate and defense-independent pitching quality are the best indicators of ERA performance
- **FIP and xFIP** being top features validates that ERA is largely driven by controllable pitching outcomes (walks, strikeouts, home runs)
- **Win percentage** and **run differential** had moderate importance, confirming that good pitching correlates with winning
- The model achieved **88.5% accuracy** on a balanced test set (48 Good, 48 Bad ERA teams)

---

## Technologies Used

- Python, Jupyter Notebook
- pandas, numpy
- scikit-learn (RandomForestClassifier)
- matplotlib

