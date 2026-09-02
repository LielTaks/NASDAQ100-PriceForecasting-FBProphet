# Nasdaq-100 Futures Forecasting with Prophet

A Python time-series project that explores hourly Nasdaq-100 E-mini futures data and uses Meta Prophet to forecast closing-price trends. The notebook covers data inspection, filtering, visualization, Prophet-compatible preprocessing, model training, and forecast visualization.

## Project Overview

This project demonstrates an end-to-end exploratory forecasting workflow for financial market data. It works with hourly OHLCV observations for the continuous Nasdaq-100 E-mini futures contract (`CME_MINI:NQ1!`) and models the historical closing-price series with Prophet.

The project is designed to showcase practical skills in:

- Financial time-series analysis
- Data cleaning and transformation with pandas
- Static and interactive data visualization
- Forecasting with Meta Prophet
- Communicating model output and uncertainty

## Dataset

The notebook expects a CSV file named `NQ_in_1_hour.csv` containing hourly market observations.

| Property | Value |
| --- | --- |
| Instrument | Nasdaq-100 E-mini continuous futures (`CME_MINI:NQ1!`) |
| Frequency | Hourly |
| Observations | 10,504 |
| Date range | 1 January 2024 to 10 October 2025 |
| Features | `datetime`, `symbol`, `open`, `high`, `low`, `close`, `volume` |
| Forecast target | Closing price |

> The market-data CSV is not included in this repository. Use data you are licensed to access and update the notebook's file path when necessary.

## Workflow

1. Import the analysis and forecasting libraries.
2. Load and inspect the hourly OHLCV dataset.
3. Select, summarize, and filter price columns.
4. Convert timestamps into a time-series-friendly format.
5. Visualize closing-price history with Matplotlib and Plotly.
6. Rename `datetime` to `ds` and `close` to `y`, as required by Prophet.
7. Fit a Prophet model to the historical closing prices.
8. Generate a 365-period forecast with uncertainty intervals.
9. Visualize the overall forecast and its trend and seasonal components.

## Repository Structure

```text
.
├── Untitled1.ipynb       # Data exploration, visualization, and forecasting
└── README.md             # Project documentation
```

For a more polished portfolio repository, rename the notebook to `nasdaq_futures_forecasting.ipynb`.

## Technologies

- Python 3
- Jupyter Notebook or Google Colab
- pandas
- Prophet
- Matplotlib
- Plotly

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/oluwatimilehintomoloju/nasdaq-futures-forecasting-prophet.git
cd nasdaq-futures-forecasting-prophet
```

### 2. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows, activate it with:

```powershell
.venv\Scripts\activate
```

### 3. Install the dependencies

```bash
pip install pandas prophet matplotlib plotly notebook
```

### 4. Add the dataset

Create a `data` directory and place the CSV inside it:

```text
data/NQ_in_1_hour.csv
```

Then replace the Google Colab path in the notebook:

```python
df = pd.read_csv("/content/NQ_in_1_hour.csv")
```

with a repository-relative path:

```python
df = pd.read_csv("data/NQ_in_1_hour.csv")
```

### 5. Run the notebook

```bash
jupyter notebook Untitled1.ipynb
```

Run the cells in order to reproduce the analysis and forecast.

## Model Output

The Prophet model produces:

- `yhat` — predicted closing price
- `yhat_lower` — lower uncertainty bound
- `yhat_upper` — upper uncertainty bound
- Forecast charts combining historical observations and predictions
- Trend and seasonal component plots
- An interactive Plotly forecast visualization

The notebook is an exploratory forecasting exercise. It does not currently report holdout-set accuracy, trading performance, or investment returns.

## Limitations and Future Improvements

- Add a chronological train, validation, and test split.
- Evaluate forecasts with MAE, RMSE, and MAPE.
- Set the forecast frequency explicitly to match the intended hourly or daily horizon.
- Tune Prophet seasonality and changepoint parameters.
- Compare Prophet with statistical and machine-learning baselines.
- Engineer return, volatility, volume, and technical-indicator features.
- Add reproducible dependency versions in `requirements.txt`.
- Save publication-ready charts for display on the portfolio site.
- Investigate market-session gaps, contract rolls, and timezone handling.

## Portfolio Summary

> Built a Python forecasting workflow for 10,504 hourly Nasdaq-100 E-mini futures observations using pandas, Prophet, Matplotlib, and Plotly. Prepared OHLCV time-series data, explored price behaviour, generated future estimates with uncertainty intervals, and visualized trend and seasonal components.

## Disclaimer

This project is for educational and research purposes only. Forecasts are inherently uncertain and should not be interpreted as financial advice or used as the sole basis for trading decisions. Historical patterns do not guarantee future results.

## Author

**Liel Takawira**

- GitHub: [@LielTaks](https://github.com/LielTaks)

## License

No license has been specified. Unless a license is added, all rights are reserved by the repository owner. Any market data remains subject to its provider's terms and licensing requirements.
