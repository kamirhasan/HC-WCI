# HC-WCI: Human Capital Wealth Capacity Index
## Replication Repository

**Paper:** Human Capital and Housing Finance: Validating an Alternative
Mortgage Qualification Framework for U.S. Immigrant Borrowers
**Author:** Amir Hasan Khan, Wright State University
**Journal:** Economic Analysis and Policy (submitted 2026)

---

## Overview

This repository contains all code and processed data to replicate the HC-WCI
analysis. The HC-WCI predicts immigrant mortgage acquisition propensity using
three observable variables: education tier (E), years of U.S. residency (T),
and a geospatially normalised Rent Performance Ratio (Rp).

---

## Data Sources (raw files not included — obtain directly)

| Dataset | Source | URL |
|---|---|---|
| ACS 2014-2024 | IPUMS USA | https://usa.ipums.org |
| AHS 2023 | U.S. Census Bureau | https://census.gov/programs-surveys/ahs |
| SCF 2016/2019/2022 | Federal Reserve Board | https://federalreserve.gov/econres/scfindex.htm |

---

## Run Order

1. `notebooks/Data_Extraction_Code.ipynb` — ACS microdata → cohort dataset
2. `notebooks/HC_WCI_Extraction_CLEAN_FINAL.ipynb` — AHS + SCF extraction
3. `notebooks/HC_WCI_Analysis_FINAL.ipynb` — ML models + paper tables/figures

---

## Setup

```bash
python -m venv hcwci_env
source hcwci_env/bin/activate   # Windows: hcwci_env\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

---

## Key Results

| Finding | Value |
|---|---|
| Model D R² (HC-WCI: Years + Education) | 14.02% [CI: 12.30%, 15.62%] |
| Model C R² (Income baseline) | 5.59% [CI: 3.94%, 6.94%] |
| R² improvement | +8.43 pp (151%) |
| AHS late payment risk reduction (Q4 vs Q1) | 46.2% (p<0.001) |
| SCF credit exclusion: Some HS vs Bachelor+ | 29.6% → 8.5% |

---

## Citation

Khan, A. H. (2026). Human capital and housing finance: Validating an
alternative mortgage qualification framework for U.S. immigrant borrowers.
*Economic Analysis and Policy*. [Under review]

---

## Declaration

AI tools (Anthropic Claude and Google Gemini) assisted with Python script
generation. All code was reviewed, tested, and validated by the author.

## License
MIT License — see LICENSE file.
