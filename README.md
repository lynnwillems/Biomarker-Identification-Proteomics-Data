# Biomarker Identification Proteomics Data
This repository contains a Python script for identifying potential biomarkers from a proteomic dataset, comparing pulmonary vascular lesions from CTEPH patients to control pulmonary artery samples.
![image](https://github.com/user-attachments/assets/575cd342-c12d-44d4-89cf-892a943b705e)


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
1. Original (Non-Imputed) Dataset
This dataset was used to filter proteins with >10% missing values across samples are excluded from downstream analysis (tabular .csv or .tsv file). Rows were protein identifiers and colums were different samples. 

Rows: Protein identifiers

Columns: Sample intensity values

2. Imputed Dataset
Purpose: Used for all downstream analyses after filtering.

Content: Same structure as the original dataset, but missing values are imputed (e.g., using DIA-Analyst’s internal methods).

Note: Only proteins passing the filtering step from the original dataset are retained.

3. Secretome Reference Dataset
Source: Uhlén, M. et al. (2019). The human secretome. Science Signaling, 12.
https://doi.org/10.1126/scisignal.aaz0274

Purpose: To annotate or filter for secreted proteins among the identified biomarkers.

Format: List of gene names or protein identifiers (e.g., UniProt IDs).![image](https://github.com/user-attachments/assets/459684d7-63e7-4250-a7d4-bbf9a798d1a5)

### Example input structure:
```
input_directory/
├── WellA01.nd2
├── WellB01.nd2
```

