# Androgen-Related Associations With CBC-Derived Inflammatory Indices in Young Women With PCOS

This repository contains the full analytical workflow for the cross-sectional study:

**“Androgen-Related Associations With CBC-Derived Inflammatory Indices in Young Women With Polycystic Ovary Syndrome.”**

The study evaluates associations between markers of androgen excess and complete blood count (CBC)–derived platelet and inflammatory indices in women with PCOS.

Primary analyses are conducted using an **available-case dataset (AC)**.  
Sensitivity analyses are performed using a **complete-case dataset (CC)**.

---

## Study Overview

### Primary Predictors
- Free Androgen Index (FAI)  
- Total testosterone  
- DHEAS  

### Primary Outcomes
- Platelet activation indices: MPV, PDW, P-LCR  
- Inflammatory indices: RDW, NLR, PLR  

### Statistical Adjustment
- Crude models  
- Insulin resistance–adjusted models: `+ log(HOMA-IR)`  
- Fully adjusted models: `+ log(HOMA-IR) + age` 

Multiple testing is controlled using **Benjamini–Hochberg false discovery rate (FDR) correction within predefined families of tests**.

Regression results are reported as:
- β coefficients  
- HC3-robust standard errors  
- 95% confidence intervals  

---

## Repository Structure

### `Piorkowska_01_exploration.ipynb`
Exploratory data analysis (EDA):
- dataset integrity checks  
- identification of key hormonal and hematologic variables  
- characterization of missingness patterns  

No exclusions are implemented at this stage.

---

### `Piorkowska_02_preprocessing.ipynb`
Data preprocessing:
- derivation of indices (FAI, NLR, PLR, MPR, HOMA-IR, etc.)  
- missingness-based variable exclusion (threshold defined in notebook)  
- biological plausibility checks  
- IQR-based outlier flagging (conservative retention policy)  
- generation of:
  - **available-case dataset (AC)**  
  - **complete-case dataset (CC)**  
- selection bias assessment (included vs excluded)

---

### `Piorkowska_03_analysis.ipynb`
Statistical analysis:
- Spearman correlations with FDR correction  
- OLS regression with HC3 robust standard errors  
- AC as primary inference dataset  
- CC as sensitivity analysis  
- Cook’s distance influence diagnostics  
- generation of manuscript-ready regression tables (β + 95% CI)

---

## Outputs

All results are stored in the `outputs/` directory.

### Key Files

- `REG_primary_models_HC3.csv`  
  All regression models (β, SE_HC3, 95% CI, p, q, R²)

- `PRIMARY_RESULTS_main_model.csv`  
  Main adjusted models used for reporting

- `PRIMARY_RESULTS_all_models.csv`  
  Full regression output across all adjustment sets

- `corr_PRIMARY_*.csv`  
  Correlation results (AC and CC; platelet and inflammatory families)

- `QC_missingness_keyvars_*.csv`  
  Missingness of variables included in regression models

- `QC_cooks_distance_primary_AC.csv`  
  Influence diagnostics (Cook’s distance summary)

- `DESCRIPTIVES_AC.csv`  
  Descriptive statistics for primary variables

If enabled, manuscript-ready exports are saved under:

