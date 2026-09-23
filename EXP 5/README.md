# Experiment 5 — Resampling Techniques and Confidence Interval Estimation for Statistical Decision Making

## Aim

To implement bootstrap and permutation resampling techniques on the Pima Indians Diabetes Dataset for estimating confidence intervals and analyzing statistical differences between groups.

## Files

| File | Description |
| --- | --- |
| `exp 5 code` | Python script for the experiment |
| `Stats exp5-04.pdf` | Lab write-up with screenshots, conclusion and answers |

## Dataset

Pima Indians Diabetes Dataset (768 patients, 9 columns). The script downloads it from:

```text
https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv
```

An internet connection is required.

## What the script does

1. **Bootstrap resampling:** draws 10,000 samples with replacement from the Glucose values and calculates the mean of each.
2. Builds a **95% percentile bootstrap confidence interval** (2.5th and 97.5th percentiles) and plots the bootstrap distribution.
3. Splits patients into diabetic (`Outcome = 1`) and non-diabetic (`Outcome = 0`) groups and calculates the observed difference in mean Glucose.
4. **Permutation test:** shuffles the group labels 10,000 times to build the null distribution of the difference, then calculates a two-sided p-value.
5. Plots the permutation distribution with the observed difference and makes a decision at α = 0.05.

`np.random.seed(42)` is set, so results are reproducible.

## Requirements

- Python 3.8+
- numpy, pandas, matplotlib, seaborn

```powershell
pip install numpy pandas matplotlib seaborn
```

## How to run

From inside the `EXP 5` folder:

```powershell
python "exp 5 code"
```

The script can also be pasted into a Google Colab / Jupyter notebook cell.

## Key results

| Analysis | Result |
| --- | --- |
| Original sample mean Glucose | 120.89 mg/dL |
| Bootstrap mean (10,000 samples) | 120.90 mg/dL |
| 95% bootstrap CI | (118.69, 123.12) mg/dL |
| Mean Glucose, diabetic (n = 268) | 141.26 mg/dL |
| Mean Glucose, non-diabetic (n = 500) | 109.98 mg/dL |
| Observed difference | 31.28 mg/dL |
| Permutation p-value | 0.0 (< 0.0001) |

**Decision:** Reject H₀. The difference in mean Glucose between diabetic and non-diabetic patients is statistically significant.
