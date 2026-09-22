# CSD361 - Lab Assignment 1: Taxi Fare Prediction with Linear Regression

Data preprocessing and Linear Regression on the Chicago Taxi Trips (2024) dataset,
comparing Original, Min-Max normalized, and Standardized features — both with
closed-form OLS and gradient descent implemented from scratch.

## Contents
- `CSD361_Lab1_TaxiFare_Regression.ipynb` — full notebook (code + outputs + plots)
- `CSD361_Lab1_Report.pdf` — write-up with discussion answers
- `figs/` — saved plot images

## Dataset
Chicago Taxi Trips (2024), from the [Chicago Data Portal](https://data.cityofchicago.org/Transportation/Taxi-Trips-2024-/ajtu-isnz).
Not included in this repo (large file) — download it from the link above and place
it in the project root as `Taxi_Trips_-_2024_20240408.csv` before running the notebook.

## How to run
1. Clone this repo
2. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn`
3. Download the dataset (see above) into the repo root
4. Open `CSD361_Lab1_TaxiFare_Regression.ipynb` in Jupyter or Colab and run all cells

## Summary of findings
- With exact (closed-form) Linear Regression, feature scaling does not change MAE/MSE.
- With gradient descent, scaling matters a lot — unscaled features diverge at almost
  every learning rate tested, while standardized features converge fastest and most
  reliably.
- Removing IQR-based outliers improved MAE/MSE/R² on this dataset, but is a modeling
  trade-off, not an automatic improvement.