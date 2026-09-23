# Experiment 2 — Descriptive Statistics and Data Visualization for Exploratory Data Analysis

## Aim

To apply descriptive statistical measures and data visualization techniques to summarize, analyze, and interpret the distribution and relationships present in the Pima Indians Diabetes Dataset.

## Files

| File | Description |
| --- | --- |
| `exp 2 code` | Python script for the experiment |
| `diabetes (1).csv` | Pima Indians Diabetes Dataset (768 rows, 9 columns) |
| `Stats exp2-04.pdf` | Lab write-up with screenshots, conclusion and answers |

## Dataset

Pima Indians Diabetes Dataset: diagnostic measurements for 768 female patients, with 8 input attributes and a binary `Outcome` (1 = diabetic, 0 = non-diabetic).

The script reads `diabetes.csv`, so rename `diabetes (1).csv` to `diabetes.csv` before running.

## What the script does

1. Loads the dataset and prints the first/last 5 rows, shape, column names, data types, `info()` and missing values.
2. Calculates descriptive statistics: summary, mean, median, mode, minimum, maximum, variance, standard deviation and range.
3. Plots histograms and boxplots for all numerical variables (combined and one boxplot per variable).
4. Plots a bar chart of the `Outcome` frequency.
5. Plots scatter plots of Glucose vs BMI and Age vs Glucose, coloured by Outcome.
6. Plots a pair plot (Glucose, BMI, Age, BloodPressure) and a correlation heatmap.
7. Finds the variable with the highest standard deviation and the one with the largest mean–median difference.
8. Runs an IQR-based outlier check and prints the observations.

## Requirements

- Python 3.8+
- pandas, numpy, matplotlib, seaborn

```powershell
pip install pandas numpy matplotlib seaborn
```

## How to run

From inside the `EXP 2` folder (after renaming the CSV):

```powershell
python "exp 2 code"
```

The script can also be pasted into a Google Colab / Jupyter notebook cell.

## Key results

- **Highest standard deviation:** Insulin (≈ 115.24)
- **Largest mean–median difference:** Insulin (mean ≈ 79.8, median 30.5), so its distribution is strongly right-skewed.
- **Glucose:** mean 120.89, median 117, std 31.97
- **BMI:** mean 31.99, median 32.0, std 7.88
- **Age:** mean 33.24, median 29, std 11.76
- Glucose vs BMI shows a weak-to-moderate positive relationship. Higher Glucose and BMI values are more common in diabetic patients.
