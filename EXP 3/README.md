# Experiment 3 — Correlation Analysis, Distance Measures, and Data Preprocessing

## Aim

To implement correlation analysis, distance measures, and basic data preprocessing techniques on the Pima Indians Diabetes Dataset to identify relationships between variables and prepare data for further analysis.

## Files

| File | Description |
| --- | --- |
| `exp 3 code` | Python script for the experiment |
| `diabetes (1).csv` | Pima Indians Diabetes Dataset (768 rows, 9 columns) |
| `Stats exp3-04.pdf` | Lab write-up with screenshots, conclusion and answers |

## Dataset

Pima Indians Diabetes Dataset: diagnostic measurements for 768 female patients, with 8 input attributes and a binary `Outcome` (1 = diabetic, 0 = non-diabetic).

The script reads `diabetes.csv`, so rename `diabetes (1).csv` to `diabetes.csv` before running.

## What the script does

1. Loads the dataset and prints the first rows, shape and `info()`.
2. Counts invalid zero values in Glucose, BloodPressure, SkinThickness, Insulin and BMI, then replaces them with `NaN`.
3. Fills the missing values with **median imputation** (`SimpleImputer(strategy="median")`).
4. Computes the correlation matrix and plots it as a heatmap.
5. Calculates the **Euclidean, Manhattan and Cosine** distances between the first two patients.
6. Applies **standardization** (`StandardScaler`, mean 0 and std 1) and recalculates the distances.
7. Reports the strongest positive and negative correlations.

## Requirements

- Python 3.8+
- pandas **2.x**, numpy, matplotlib, seaborn, scikit-learn

```powershell
pip install "pandas<3" numpy matplotlib seaborn scikit-learn
```

The final step (strongest correlations) stops with `ValueError: underlying array is read-only` on pandas 3.x, so use pandas 2.x (as in Google Colab).

## How to run

From inside the `EXP 3` folder (after renaming the CSV):

```powershell
python "exp 3 code"
```

The script can also be pasted into a Google Colab / Jupyter notebook cell.

## Key results

Invalid zeros replaced and imputed: Glucose 5, BloodPressure 35, SkinThickness 227, Insulin 374, BMI 11.

Distances between patient 1 and patient 2:

| Measure | Before scaling | After standardization |
| --- | --- | --- |
| Euclidean | 66.90 | 3.40 |
| Manhattan | 106.28 | 8.20 |
| Cosine | 0.032 | 1.585 |

Before scaling, large-range variables (Insulin, Glucose) dominate the distances. After standardization every feature contributes equally.

- **Strongest positive correlation:** Pregnancies–Age (≈ 0.54)
- **Strongest negative correlation:** Pregnancies–DiabetesPedigreeFunction (≈ −0.03), which is very weak, so there is no meaningful negative correlation in the dataset.
