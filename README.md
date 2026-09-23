# Statistics for Machine Learning and Data Science Lab

Lab experiments for the course **Statistics for Machine Learning and Data Science Lab (2015111)**, TE-AI&DS, Semester V.

## Overview

All experiments use the **Pima Indians Diabetes Dataset**: diagnostic measurements for 768 female patients, with 8 input attributes (Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age) and a binary `Outcome` (1 = diabetic, 0 = non-diabetic).

Each experiment folder has a Python script, a lab write-up (PDF) and its own README with details and results.

## Experiments

| No. | Folder | Title | Main techniques |
| --- | --- | --- | --- |
| 1 | [EXP 1](EXP%201/README.md) | Exploratory Statistical Analysis of a Real-World Dataset (Case Study) | Data inspection, summary statistics, zero-value and IQR outlier checks, histograms, boxplots, heatmap |
| 2 | [EXP 2](EXP%202/README.md) | Descriptive Statistics and Data Visualization for EDA | Mean, median, mode, range, variance, std; histograms, boxplots, scatter plots, pair plot |
| 3 | [EXP 3](EXP%203/README.md) | Correlation Analysis, Distance Measures, and Data Preprocessing | Median imputation, correlation matrix, Euclidean/Manhattan/Cosine distance, standardization |
| 4 | [EXP 4](EXP%204/README.md) | Statistical Inference, Estimation, and Hypothesis Testing | Point estimates, confidence intervals, one-sample and two-sample t-tests, chi-square test |
| 5 | [EXP 5](EXP%205/README.md) | Resampling Techniques and Confidence Interval Estimation | Bootstrap confidence interval, permutation test |

## Repository structure

```text
EXP 1/   exp1 code,    diabetes.csv,      Stats exp1-04.pdf, README.md
EXP 2/   exp 2 code,   diabetes (1).csv,  Stats exp2-04.pdf, README.md
EXP 3/   exp 3 code,   diabetes (1).csv,  Stats exp3-04.pdf, README.md
EXP 4/   exp 4 code,   diabetes.csv,      Stats exp4-04.pdf, README.md
EXP 5/   exp 5 code,                      Stats exp5-04.pdf, README.md
```

## Requirements

- Python 3.8+
- pandas, numpy, matplotlib, seaborn, scipy, scikit-learn

```powershell
python -m venv .venv
.\.venv\Scripts\pip install "pandas<3" numpy matplotlib seaborn scipy scikit-learn
```

pandas 2.x is recommended, because Experiment 3 fails on pandas 3.x.

## How to run

The code files have no `.py` extension, but Python runs them directly. Run each one from inside its folder:

```powershell
cd "EXP 1"
python "exp1 code"
```

```powershell
cd "EXP 4"
python "exp 4 code"
```

The scripts can also be pasted into a Google Colab or Jupyter notebook cell.

## Dataset notes

- **Experiments 1–3** read `diabetes.csv` from the same folder. In `EXP 2` and `EXP 3` the file is named `diabetes (1).csv`, so rename it to `diabetes.csv` before running.
- **Experiments 4–5** download the dataset from a public URL, so they need an internet connection:
  `https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv`
