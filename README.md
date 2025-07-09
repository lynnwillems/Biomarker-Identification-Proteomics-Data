# Biomarker Identification Proteomics Data
This repository contains a Python script for identifying potential biomarkers from a proteomic dataset, comparing pulmonary vascular lesions from CTEPH patients to control pulmonary artery samples.

# Requirements
This script runs in a standard Python environment. You will need:
- Python ≥ 3.7
- Required libraries, besides built-in libraries:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `scikit-image`
  - `statsmodels`
  - `scikit-learn`
 
# Input
This script is designed to analyze proteomic data obtained through DIA-Analyst, a web-based tool for data-independent acquisition (DIA) proteomics: https://analyst-suites.org/apps/dia-analyst/.
The pipeline requires three input datasets:
**1. Original (Non-Imputed) Dataset:** This dataset was used to filter proteins with >10% missing values across samples are excluded from downstream analysis (tabular .csv or .tsv file). Rows were protein identifiers and colums were different samples. 
2. Imputed Dataset: Same structure as the original dataset, but missing values are imputed (e.g., using DIA-Analyst’s internal methods). Original data can be used without imputation.
3. Secretome Reference Dataset: To annotate or filter for secreted proteins among the identified biomarkers. Source of secretome data set is Uhlén, M. et al. (2019). The human secretome. Science Signaling, 12. (https://doi.org/10.1126/scisignal.aaz0274)



