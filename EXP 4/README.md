# Experiment 4 — Statistical Inference, Estimation, and Hypothesis Testing on Real-World Datasets

## Aim

To apply statistical estimation and hypothesis testing techniques to the Pima Indians Diabetes Dataset and draw conclusions about population characteristics using sample data.

## Files

| File | Description |
| --- | --- |
| `exp 4 code` | Python script for the experiment |
| `diabetes.csv` | Local copy of the Pima Indians Diabetes Dataset (not used by the script) |
| `Stats exp4-04.pdf` | Lab write-up with screenshots, conclusion and answers |

## Dataset

Pima Indians Diabetes Dataset (768 patients, 9 columns). The script downloads it from:

```text
https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv
```

An internet connection is required.

## What the script does

1. **Point estimation:** sample mean of Glucose and sample proportion of diabetic patients.
2. **Confidence intervals:**
   - 95% CI for mean Glucose using the t-distribution
   - 95% CI for the diabetes proportion using the z-distribution
3. **One-sample t-test:** is the mean Glucose different from 120 mg/dL?
4. **Two-sample (Welch's) t-test:** is the mean BMI different between diabetic and non-diabetic patients?
5. **Chi-square test of independence:** is BMI category (Normal < 25, Overweight 25–30, Obese > 30) associated with diabetes outcome?
6. Plots a Glucose histogram with the reference line at 120, a BMI boxplot by Outcome and a BMI category vs Outcome count plot.

All tests use a significance level of α = 0.05.

## Requirements

- Python 3.8+
- pandas, numpy, scipy, matplotlib, seaborn

```powershell
pip install pandas numpy scipy matplotlib seaborn
```

## How to run

From inside the `EXP 4` folder:

```powershell
python "exp 4 code"
```

The script can also be pasted into a Google Colab / Jupyter notebook cell.

## Key results

| Analysis | Result |
| --- | --- |
| Sample mean Glucose | 120.89 mg/dL |
| 95% CI for mean Glucose | (118.63, 123.16) mg/dL |
| Sample proportion diabetic | 268 / 768 = 0.349 (34.9%) |
| 95% CI for proportion | (0.315, 0.383) |
| One-sample t-test (μ = 120) | t = 0.775, p = 0.438 → **fail to reject H₀** |
| Two-sample t-test (BMI) | Mean BMI 35.14 (diabetic) vs 30.30 (non-diabetic); t = 8.62, p ≈ 6.6 × 10⁻¹⁷ → **reject H₀** |
| Chi-square (BMI category × Outcome) | χ² = 75.17, df = 2, p ≈ 4.7 × 10⁻¹⁷ → **reject H₀** |

**Conclusions:** There is no evidence that mean glucose differs from 120 mg/dL. Diabetic patients have a significantly higher BMI, and BMI category is significantly associated with diabetes.
