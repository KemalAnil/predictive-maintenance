🚀 Predictive Maintenance with C-MAPSS (FD001–FD004)

This repository implements an end-to-end Remaining Useful Life (RUL) prediction workflow using the NASA C-MAPSS turbofan engine degradation datasets.
It includes preprocessing, leakage-free splitting, normalization, model training, evaluation, and visualization.

Supported datasets: FD001, FD002, FD003, FD004

📂 Repository Structure
predictive-maintenance/
│
├── notebooks/
│   ├── Baseline_CMAPSS_FD001.ipynb
│   ├── Baseline_CMAPSS_FD002.ipynb
│   ├── Baseline_CMAPSS_FD003.ipynb
│   └── Baseline_CMAPSS_FD004.ipynb
│
├── data/
│   └── CMAPSS/ (place dataset files here)
│
├── requirements.txt
└── README.md

📘 Included Notebooks

Each notebook contains a complete baseline pipeline for one dataset variant.

FD001 — Single fault, single operating condition

notebooks/Baseline_CMAPSS_FD001.ipynb

Load FD001 dataset

Compute RUL + early warning labels

Leakage-free split by engine

Z-score scaling

RandomForest (regression + classification)

RMSE, R², confusion matrix, precision/recall/F1

FD002 — Single fault, multiple operating conditions

notebooks/Baseline_CMAPSS_FD002.ipynb

Same pipeline as FD001

Cluster-based normalization for 6 operating regimes

FD003 — Multiple faults, single operating condition

notebooks/Baseline_CMAPSS_FD003.ipynb

Handles two fault modes

Same preprocessing + modeling flow

FD004 — Multiple faults, multiple operating conditions

notebooks/Baseline_CMAPSS_FD004.ipynb

Multi-fault + multi-regime

Combines FD002 and FD003 preprocessing techniques

📊 Baseline Pipeline Overview

All notebooks implement:

Load raw C-MAPSS sensor time-series

Clean and format run-to-failure data

Compute RUL targets

Create early-warning labels (e.g., RUL ≤ 30)

Split engines without leakage

Normalize features

Train:

RUL regression model

Warning classifier

Evaluate using:

RMSE, MAE, R²

Confusion matrix

Precision / Recall / F1

▶️ How to Run
1. Install Python 3.10+
2. Install dependencies
pip install -r requirements.txt

3. Download the NASA C-MAPSS dataset

Place these files into:

data/CMAPSS/


For example:

train_FD001.txt
test_FD001.txt
RUL_FD001.txt
...

4. Run any notebook

Open using Jupyter Notebook or VS Code:

notebooks/Baseline_CMAPSS_FD001.ipynb


and similarly for FD002–FD004.

🧠 Dataset Overview
Dataset	Operating Conditions	Fault Modes	Difficulty
FD001	1	1	Easy
FD002	6	1	Medium
FD003	1	2	Medium
FD004	6	2	Hard
📌 Future Work

LSTM / GRU deep learning models

CNN-based time-series models

Unified Python training script

Model comparison dashboards

Deployment-ready RUL inference API
