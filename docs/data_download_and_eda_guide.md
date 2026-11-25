# Market Stress Regimes — Data Download & EDA

This project uses monthly FRED data from **January 2010 to October 2026**. These two notebooks cover **Z1–Z3** (the first three explanatory variables).

## 1. Setup

Open a terminal in the project folder and install the dependencies:

```bash
python -m pip install -r requirements.txt
```

Open the `notebooks/` folder in VS Code or start Jupyter Lab from the project folder:

```bash
jupyter lab
```

## 2. Download the data

Open **`notebooks/01_download_z1_z3.ipynb`** and run all cells in order. Internet access is required.

The notebook downloads FRED series and constructs:

- **Z1 — Yield curve:** `T10Y2Y` (monthly average)
- **Z2 — Credit spread:** `BAA10YM - AAA10YM`
- **Z3 — Unemployment change:** monthly change in `UNRATE`

Files are saved automatically:

- `data/raw/fred/` — original downloaded series
- `data/interim/z1_z3_levels_monthly.csv` — monthly source data
- `data/processed/z1_z3_monthly.csv` — the three prepared variables

## 3. Run exploratory data analysis

After completing Notebook 01, open **`notebooks/02_eda_stationarity_z1_z3.ipynb`** and run all cells in order.

It provides descriptive statistics, time-series plots, correlations, ACF plots, and **ADF/KPSS stationarity tests**. Formal stationarity tests use **2010–2020 training data**, keeping 2021–2026 separate for later forecast evaluation.

Results are saved to:

- `reports/eda_descriptive_train.csv`
- `reports/stationarity_results_train.csv`

## 4. Sharing with the team

Share **`data/processed/z1_z3_monthly.csv`** with your teammate. It uses a monthly `date` column and can be merged with their Z4–Z6 data on `date`.
