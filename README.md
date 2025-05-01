# 📈 Bitcoin Price Forecasting with SARIMA
This project explores time series forecasting using the Seasonal ARIMA (SARIMA) model applied to Bitcoin's historical closing prices. It combines statistical modeling, visualization, and model evaluation to predict future trends in a log-transformed price series.

## 📁 Dataset

The dataset contains the historical closing prices of Bitcoin from 2017 to 2023.
**Source:** Kaggle
https://www.kaggle.com/datasets/lucamu79/bitcoin-price-prediction-using-a-sarima-model/data

**Columns**:
- `Date`: Date of the record.
- `Close`: Closing price of Bitcoin in USD.

## 🔍 Objectives
- Load and explore Bitcoin price time series data
- Understand the data's trend, seasonality, and stationarity
- Transform and preprocess the data for modeling
- Fit and tune SARIMA models using grid search
- Evaluate models using AIC/BIC and residual diagnostics
- Forecast future prices and plot with confidence intervals

## 📂 Project Structure
'''
├── scripts
  ├──Bitcoin_Prices.ipynb    # Main Jupyter notebook
├── README.md               # This file
├── data
  ├── BTC-USD prices 2017-2023 CLOSE #dataset
'''
## 🧰 Technologies Used
Python 3.x

Jupyter Notebook

pandas, numpy, matplotlib, seaborn — for data handling and plotting

statsmodels — for SARIMA modeling

pmdarima — for optional automated model selection

itertools, warnings — for grid search and clean output

## 🧪 Methodology
1. Data Loading & Exploration
Read in historical Bitcoin daily close prices.

Resample and clean the data to obtain monthly prices, using only the first day of each month to reflect a structured time index.

2. Visualization
Decompose the time series using STL and classical decomposition.

Plot seasonal, trend, and residual components.

Observe annual patterns and long-term trends.

3. Stationarity Check
Apply the Augmented Dickey-Fuller (ADF) test to check for stationarity.

Use log transformation and differencing as needed to stabilize variance and remove trends.

4. ACF and PACF
Plot autocorrelation (ACF) and partial autocorrelation (PACF) to guide model order selection.

Visual diagnostics indicate the need for AR(1) and MA(1) terms, along with potential seasonality.

5. SARIMA Modeling
Use manual grid search over possible (p, d, q) and (P, D, Q, s) parameters.

Target annual seasonality (s=12) assuming monthly data.

Fit multiple models and compare AIC and BIC values to find the optimal configuration.

6. Best Model Example Output
text
Copy
Edit
Best SARIMA: Order=(1, 0, 0), Seasonal=(0, 0, 0, 12)
AIC: -9334.96
BIC: -9323.27
Log Likelihood: 4669.48
7. Forecasting
Forecast 12 future months of Bitcoin prices.

Inverse-transform predictions from log space back to real prices.

Plot results with 95% confidence intervals.

## 📈 Results & Conclusions
A log-transformed SARIMA(1,0,0) model without seasonality significantly outperformed more complex seasonal models.

The transformation made the series more stationary, and the low AIC/BIC indicates excellent fit.

The seasonal model (SARIMA(0,1,1)x(1,1,1,12)) was overfitting, with very high AIC and unstable coefficients.

Conclusion: Simpler models with proper transformation can outperform overly complex seasonal ones.

## 📉 Sample Forecast Plot




📝 License
This project is licensed under the MIT License.
