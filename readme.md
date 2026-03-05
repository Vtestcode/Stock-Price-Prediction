# Stock Price Prediction Dashboard

A Dash-based web app that combines:
- `LSTM` next-price inference for Tata Global (`NSE-TATA.csv` + `saved_model.h5`)
- Interactive market charts for selected US stocks (`stock_data.csv`)

## Why This Project
This app demonstrates an end-to-end stock analytics workflow:
- Data loading and preprocessing
- Sequence-based prediction with a trained neural network
- Interactive visualization with Plotly Dash

## Features
- Actual vs predicted closing price visualization (Tata Global)
- Multi-select comparison of high/low prices
- Multi-select market volume trends
- Date range slider and range selector controls

## Tech Stack
- Python
- Dash
- Plotly
- Pandas
- NumPy
- scikit-learn (`MinMaxScaler`)
- Keras (model loading)

## Project Structure
```text
.
|-- stock_app.py
|-- stock.ipynb
|-- Tesla.csv
|-- saved_model.h5           # required by app (ignored by git)
|-- NSE-TATA.csv             # required by app
|-- stock_data.csv           # required by app
|-- .gitignore
```

## Prerequisites
- Python 3.10+ recommended
- A virtual environment
- Required data/model files present in project root:
  - `NSE-TATA.csv`
  - `stock_data.csv`
  - `saved_model.h5`

## Quick Start (PowerShell)
```powershell
# 1) Create and activate venv
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1

# 2) Install dependencies
py -m pip install --upgrade pip
py -m pip install dash plotly pandas numpy scikit-learn tensorflow keras

# 3) Run app
py stock_app.py
```

Open the local URL printed in terminal (typically `http://127.0.0.1:8050`).

## How It Works
1. Reads Tata dataset and sorts by date.
2. Scales close prices with `MinMaxScaler`.
3. Loads pre-trained model from `saved_model.h5`.
4. Builds 60-timestep windows for prediction.
5. Plots actual and predicted closing prices.
6. Adds interactive high/low and volume charts for selected symbols.

## Current Limitations
- File name references in `stock_app.py` are strict and case-sensitive by environment.
- Train/validation split is hardcoded (`0:987` and `987:`).
- App expects model + CSV files in root directory.
- No `requirements.txt` lock file yet.

## Recommended Next Steps
- Add `requirements.txt` and pin package versions.
- Move configuration (paths, split ratio, window size) to constants/env vars.
- Add input validation and graceful error messages for missing files.
- Add unit tests for preprocessing and sequence generation.

## Author
Visha
