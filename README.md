# Biomarker Identification Proteomics Data
This repository provides a complete Python-based pipeline to identify and validate potential biomarkers from a **DIA proteomics dataset** of pulmonary vascular lesions in **CTEPH** patients compared to control pulmonary arteries.

The analysis includes:
- Protein filtering (proteins with >10% missing values in the original dataset are excluded)
- Robust differential expression (DE) testing using 50-split stratified train/test for each group vs control (t-test with FDR correction).
- Selection of consistently significant up- or downregulated proteins 
- Integration with the **human secretome** dataset
- Final validation of a 3-marker panel (**THBS1 + SOD3 + NID1**) using bootstrapped logistic regression (100 iterations) with AUC, sensitivity, specificity, PPV, and NPV.

## Requirements
This script runs in a standard Python environment. You will need:
- Python ≥ 3.7
- Required libraries:
  - `numpy`
  - `pandas`
  - `scipy`
  - `statsmodels`
  - `scikit-learn`
 
## Input
This script is designed to analyze proteomic data obtained through DIA-Analyst, a web-based tool for data-independent acquisition (DIA) proteomics: https://analyst-suites.org/apps/dia-analyst/.
The pipeline requires three input datasets:

**1. Original (Non-Imputed) Dataset:** 
- Used to filter proteins with >10% missing values across samples.
- Format: .csv or .tsv file

**2. Imputed Dataset:** 
- Used for all downstream analysis after filtering
- Format: .csv or .tsv file

**3. Secretome Reference Dataset:** 
- Used to filter for secreted proteins among the identified biomarkers.
- Source secretome: Uhlén, M. et al. (2019). The human secretome. Science Signaling, 12. (https://doi.org/10.1126/scisignal.aaz0274)

## Output
- summary_df: Table of consistently significant DE genes with log2FC and direction
- Console output of matched secretome genes
    - Note: Adjust 'selected_genes' in script accordingly to console output
- Final model evaluation table in Excel: bootstrap_summary.xlsx


