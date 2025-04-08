# Bitcoin Price Forecasting with SARIMA

This project uses a SARIMA model to forecast Bitcoin (BTC-USD) closing prices using historical data from 2017 to 2023.

## 📁 Dataset

The dataset contains the historical closing prices of Bitcoin from 2017 to 2023.

**Filename**: `BTC-USD prices 2017-2023 CLOSE.csv`

**Columns**:
- `Date`: Date of the record.
- `Close`: Closing price of Bitcoin in USD.

## 📈 Model

We use the **Seasonal AutoRegressive Integrated Moving Average (SARIMA)** model to account for seasonality and trend in time series.

### Features:
- Handles missing data by interpolation.
- Visualizes the original time series and forecasts.
- Uses `pmdarima` to automatically identify optimal SARIMA parameters.

## 🛠️ Dependencies

Install dependencies using pip:

```bash
pip install pandas matplotlib seaborn statsmodels pmdarima
