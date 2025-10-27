\# Predictive Maintenance CM1 (C-MAPSS FD001)



\## What’s here

\- `notebooks/Baseline\_CM1\_CMAPSS.ipynb` – end-to-end baseline:

&nbsp; - load C-MAPSS FD001

&nbsp; - make RUL + warning labels (RUL ≤ 30)

&nbsp; - leakage-free split by engine

&nbsp; - scaling (z-score)

&nbsp; - RandomForest regressor (RUL) + classifier (warning)

&nbsp; - metrics (RMSE, R², confusion matrix, precision/recall/F1)



\## How to run

1\. Install Python 3.10+ and:

&nbsp;  ```bash

&nbsp;  pip install -r requirements.txt



