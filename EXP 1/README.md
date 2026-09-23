# Experiment 1 — Exploratory Statistical Analysis of a Real-World Dataset (Case Study)

## Aim

To perform exploratory statistical analysis of the Pima Indians Diabetes Dataset by examining its structure, variable types, data quality, statistical characteristics, and important patterns.

## Files

| File | Description |
| --- | --- |
| `exp1 code` | Python script for the experiment |
| `diabetes.csv` | Pima Indians Diabetes Dataset (768 rows, 9 columns) |
| `Stats exp1-04.pdf` | Lab write-up with screenshots, conclusion and answers |

## Dataset

Pima Indians Diabetes Dataset: diagnostic measurements for 768 female patients, with 8 input attributes (Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age) and a binary `Outcome` (1 = diabetic, 0 = non-diabetic).

The script reads `diabetes.csv` from the same folder.

## What the script does

1. Loads the dataset and prints its shape, column names, data types and first 5 records.
2. Classifies the variables as numerical or binary (`Outcome`).
3. Prints the statistical summary (`describe`), median, variance and standard deviation.
4. Checks for missing values and counts zero values in Glucose, BloodPressure, SkinThickness, Insulin and BMI.
5. Counts possible outliers in each column using the IQR (1.5 × IQR) rule.
6. Plots histograms, boxplots, an Outcome count plot, a correlation heatmap and a Glucose vs BMI scatter plot.

## Requirements

- Python 3.8+
- pandas, matplotlib, seaborn

```powershell
pip install pandas matplotlib seaborn
```

## How to run

From inside the `EXP 1` folder:

```powershell
python "exp1 code"
```

The script can also be pasted into a Google Colab / Jupyter notebook cell.

## Key results

- No missing (null) values, but zero values that are not physiologically possible:

  | Column | Zero values |
  |---|---|
  | Glucose | 5 |
  | BloodPressure | 35 |
  | SkinThickness | 227 |
  | Insulin | 374 |
  | BMI | 11 |

- Possible outliers (IQR method): Pregnancies 4, Glucose 5, BloodPressure 45, SkinThickness 1, Insulin 34, BMI 19, DiabetesPedigreeFunction 29, Age 9.
- 500 non-diabetic and 268 diabetic patients.
- Glucose has the strongest correlation with Outcome (≈ 0.47).

## Notes

- Zero values are only reported here, not replaced or imputed. Imputation is done in Experiment 3.
