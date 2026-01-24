# pcos-cbc-insulin-resistance
Analysis code for a cross-sectional study examining associations between CBC-derived leukocyte differential indices and insulin resistance in women with polycystic ovary syndrome (PCOS).

# CBC-derived leukocyte differential indices and insulin resistance in PCOS

This repository contains the analysis code for a cross-sectional study examining associations between complete blood count (CBC)–derived leukocyte differential indices and insulin resistance in women with polycystic ovary syndrome (PCOS).

## Repository contents
- `Piorkowska_01_exploratory.ipynb` — exploratory data analysis and initial inspection
- `Piorkowska_02_preprocessing.ipynb` — data preprocessing, variable derivation, and missingness assessment
- `Piorkowska_Jonczyk_03_statistical_analysis.ipynb` — correlation analyses, FDR correction, multivariable regression with HC3 robust standard errors, and sensitivity analyses

## Data availability
The clinical dataset used in this study is **not publicly available** due to ethical and data protection restrictions. De-identified data may be made available from the corresponding author upon reasonable request and subject to institutional approval.

## Reproducibility
The notebooks are intended to be run in the following order:
1. `Piorkowska_01_exploratory.ipynb`
2. `Piorkowska_02_preprocessing.ipynb`
3. `Piorkowska_Jonczyk_03_statistical_analysis.ipynb`

All statistical analyses were performed in Python. 

## Contact
Corresponding author: natalia.piorkowska@pwr.edu.pl
