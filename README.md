# HSE751-ReproducibilityExercise

# Diabetes Risk Factor Analysis

This repository includes a reproducible Python notebook (`diabetes_risk_factor_analysis (2).ipynb`) that explores which patient characteristics are associated with diabetes status

This is an exploratory analysis for workflow demonstration only. Not a clinical decision tool.

## Purpose
Research questions: (1) how do patient characteristics differ between patients with and without diabetes; (2) does mean glucose differ between the groups; (3) is obesity (BMI ≥ 30) associated with diabetes.

## Dataset
* **File:** `Example Dataset_Diabetes.csv` — 768 patients × 9 columns, from the HSE 751 Reproducibility Exercise course materials.
* **Origin:** matches the structure and size of the Pima Indians Diabetes Database (NIDDK / UCI; Smith et al., 1988): women aged 21+, Pima Indian heritage. This is inferred from the dataset's structure (the CSV has no metadata) — confirm before use beyond the exercise. Three columns were renamed in this copy.
* **Required columns (exact names):** `Pregnancies, Glucose, D_BP, Skin_Thickness, Insulin, BMI, Pedigree, Age, Outcome` (`Outcome`: 1 = diabetes, 0 = no diabetes).
* **Requirements:** numeric values, no blank cells, `Outcome` coded 0/1.

## Software
| Package | Minimum |
|---|---|
| Python | 3.9 |
| pandas | 2.0 |
| numpy | 1.24 | 
| matplotlib | 3.7 | 
| scipy | 1.11 |

The notebook's setup cell installs any missing package automatically (nothing is installed if requirements are already met). To install manually:
```bash
pip install "pandas>=2.0" "numpy>=1.24" "matplotlib>=3.7" "scipy>=1.11" jupyterlab
```

## How to run
1. **Jupyter / VS Code:** save `Example Dataset_Diabetes.csv` in the same folder as the notebook.
   **Google Colab:** upload the notebook; either upload the CSV in the Files panel first, or run all and upload it when the dialog appears.
2. Run from a clean state: **Runtime → Restart session and run all** (Colab) or **Kernel → Restart Kernel and Run All Cells** (Jupyter/VS Code).
3. The run is successful if there are no errors and Sections 3 and 4 print `✔ Validation passed` and `✔ Preparation verified`.

## Notebook contents
Setup and Environment → Data Source and Provenance (with data loading) → Data Validation → Data Preparation → Analysis (descriptive statistics, histograms, two bivariate plots, Spearman correlation matrix and heatmap, Welch's *t*-test, chi-square test, ML problem formalization, reproducibility check) → Results → Conclusions.

## Expected outputs
* **Tables:** package versions, data validation and zero counts, descriptive statistics (overall and by outcome), obesity vs diabetes counts, a seeded 8-patient sample.
* **Figures (5):** glucose histogram, BMI histogram, glucose box plot by outcome, glucose vs BMI scatter plot, Spearman correlation heatmap.

## Reproducibility
A fixed seed (`SEED = 42`) controls the sample and the bootstrap, and the data are validated before analysis.

## Assumptions and limitations
* The dataset and flow is for one specific population, so results may not apply to other sites.
* Cross-sectional data: associations are not causal. Glucose is part of the diagnostic definition of diabetes, so its association with `Outcome` is partly built in. Confirm the definition of `Outcome` in the source documentation.
* Tests are unadjusted for other variables; no multiple-testing correction; no predictive model is built.
* Written interpretations quote numbers for the example dataset; tables and figures are computed live.

To use your own data, put your file in the notebook folder and update `DATA_FILE`, the expected values in the validation cell, and the written interpretations. 
