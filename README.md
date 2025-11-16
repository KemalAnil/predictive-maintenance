# Predictive Maintenance with C-MAPSS (FD001–FD004)

This repository implements an end-to-end Remaining Useful Life (RUL) prediction pipeline using the NASA C-MAPSS turbofan engine degradation datasets.

Supported dataset variants: **FD001, FD002, FD003, FD004**

---

## Repository Structure

```text
predictive-maintenance/
├── notebooks/
│   ├── Baseline_CMAPSS_FD001.ipynb
│   ├── Baseline_CMAPSS_FD002.ipynb
│   ├── Baseline_CMAPSS_FD003.ipynb
│   └── Baseline_CMAPSS_FD004.ipynb
├── data/
│   └── CMAPSS/
├── requirements.txt
└── README.md
```

## Included Notebooks

### FD001 — Single fault, single operating condition
**File:** `notebooks/Baseline_CMAPSS_FD001.ipynb`

- Load dataset  
- Compute RUL + warning labels  
- Leakage-free split (per engine)  
- Z-score scaling  
- RandomForest regression + classification  
- Evaluation metrics: RMSE, R², precision, recall, F1, confusion matrix  

---

### FD002 — Single fault, multiple operating conditions
**File:** `notebooks/Baseline_CMAPSS_FD002.ipynb`

- Same pipeline as FD001  
- Cluster-based normalization for 6 operating regimes  

---

### FD003 — Multiple faults, single operating condition
**File:** `notebooks/Baseline_CMAPSS_FD003.ipynb`

- Two fault modes  
- Same RUL + early-warning labeling  

---

### FD004 — Multiple faults, multiple operating conditions
**File:** `notebooks/Baseline_CMAPSS_FD004.ipynb`

- Multi-fault + multi-regime  
- Combines FD002 and FD003 preprocessing logic  

---

## Baseline Pipeline Overview

All notebooks include:

- Load and clean C-MAPSS time-series data  
- Compute Remaining Useful Life (RUL)  
- Create early-warning labels (e.g., RUL ≤ 30)  
- Leakage-free train/test split by engine ID  
- Normalize features (z-score or cluster-wise)  
- Train RandomForest models  
- Evaluate:
  - RMSE / MAE  
  - R²  
  - Precision / Recall / F1  
  - Confusion matrix  
- Visualize:
  - Feature importance  
  - RUL predictions vs ground truth  
  - Warning classification results  



