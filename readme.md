# Stock Price Prediction Dashboard

This project runs a Dash web app that visualizes stock data and uses an LSTM model (`saved_model.h5`) to show predicted closing prices.

## Project Files

- `stock_app.py` - Dash application
- `saved_model.h5` - Pretrained LSTM model
- `NSE-Tata.csv` - NSE Tata historical data
- `stock_data.csv` - Multi-stock dataset used for dashboard charts
- `stock.ipynb` - Notebook (currently empty in this folder)

## Requirements

- Python 3.10 (recommended for TensorFlow compatibility)
- Virtual environment: `.venv310`

## Setup

1. Open PowerShell in the project folder:

```powershell
cd "C:\Users\Visha\OneDrive\Documents\Stock Price Prediction"
```

2. Activate the virtual environment:

```powershell
.\.venv310\Scripts\Activate.ps1
```

3. Install dependencies:

```powershell
python -m pip install dash plotly pandas numpy scikit-learn tensorflow keras h5py
```

## Important Dataset Note

`stock_app.py` reads this file name:

- `NSE-TATA.csv`

Your current file in this folder is:

- `NSE-Tata.csv`

Rename the file to match the expected name, or update the filename in `stock_app.py` line 17.

## Run the App

Use the virtual environment Python (recommended):

```powershell
.\.venv310\Scripts\python -m stock_app
```

Then open the local URL shown in terminal (usually `http://127.0.0.1:8050`).

## Troubleshooting

- `ModuleNotFoundError: No module named 'dash'`
  - You are likely using global Python. Run with `.venv310` interpreter.
- `dash_core_components` / `dash_html_components` import errors
  - The app has been updated to Dash 4-style imports (`from dash import dcc, html`).
- TensorFlow/Keras import issues
  - Use Python 3.10 kernel/environment, not Python 3.14.
