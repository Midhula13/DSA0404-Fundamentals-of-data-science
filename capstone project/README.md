# Stock Market Trend Prediction & Financial Analytics Dashboard

AI-powered stock market analysis dashboard with time series forecasting and advanced technical indicators.

## Features

- **Real-time Stock Data**: Fetch live stock data from Yahoo Finance
- **Technical Indicators**: SMA, EMA, MACD, RSI, Bollinger Bands, ATR, OBV
- **Time Series Forecasting**: ARIMA, ETS, and Moving Average prediction models
- **Trading Signals**: Automated buy/sell/hold signals based on multiple indicators
- **Market Overview**: Real-time market indices (S&P 500, Dow Jones, NASDAQ, etc.)
- **Interactive Charts**: Interactive visualization using Plotly.js
- **Support & Resistance**: Automatic detection of key price levels
- **Volatility Analysis**: Daily returns and volatility metrics

## Architecture

```
FODS/
├── main.py                 # FastAPI backend server
├── run.py                  # Application runner script
├── requirements.txt        # Python dependencies
├── src/
│   ├── utils/
│   │   └── data_fetcher.py # Data ingestion module
│   └── models/
│       └── predictor.py    # Time series analysis & ML models
├── static/
│   ├── css/
│   │   └── dashboard.css   # Dashboard styling
│   └── js/
│       └── dashboard.js    # Frontend interactivity
├── templates/
│   └── index.html          # Dashboard UI
└── data/                   # Data cache directory
```

## Technology Stack

- **Backend**: FastAPI, Uvicorn
- **Data**: yfinance, pandas, numpy
- **ML/Analytics**: scikit-learn, statsmodels
- **Visualization**: Plotly.js, Bootstrap 5
- **Frontend**: HTML5, CSS3, JavaScript

## Installation

1. Clone or download the project
2. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Run the Dashboard
```bash
python run.py
```

The dashboard will be available at `http://localhost:8000`

### Or run directly with uvicorn:
```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

## API Endpoints

- `GET /` - Dashboard UI
- `GET /api/health` - Health check
- `GET /api/stock/{symbol}/data` - Get stock data with technical indicators
- `GET /api/stock/{symbol}/info` - Get stock information
- `GET /api/stock/{symbol}/predictions` - Get predictions and analysis
- `GET /api/stock/{symbol}/signals` - Get trading signals
- `GET /api/market/indices` - Get market indices data

## How It Works

1. **Data Ingestion**: Fetches historical and real-time stock data using yfinance
2. **Technical Analysis**: Calculates 15+ technical indicators
3. **Time Series Forecasting**: Applies ARIMA, ETS, and Moving Average models
4. **Signal Generation**: Generates buy/sell signals based on indicator convergence
5. **Visualization**: Renders interactive charts and dashboards

## Prediction Models

- **ARIMA (5,1,0)**: AutoRegressive Integrated Moving Average for time series forecasting
- **ETS (Damped Trend)**: Exponential Smoothing State Space Model
- **Moving Average**: Trend-based forecasting using price momentum

## Technical Indicators

- **Moving Averages**: SMA (20, 50, 200), EMA (12, 26)
- **MACD**: Moving Average Convergence Divergence
- **RSI**: Relative Strength Index (14-period)
- **Bollinger Bands**: 20-period with 2 standard deviations
- **ATR**: Average True Range
- **OBV**: On-Balance Volume

## Project Structure

The dashboard is built with a modern architecture:
- **Backend**: FastAPI for high-performance API endpoints
- **Frontend**: Bootstrap 5 for responsive UI, Plotly.js for charts
- **Data Layer**: yfinance for data, pandas for processing
- **ML Layer**: statsmodels for time series analysis

## Supported Markets

- US Stocks (NYSE, NASDAQ)
- Indices (S&P 500, Dow Jones, NASDAQ, Russell 2000)
- Indian Indices (Nifty 50, Sensex)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Disclaimer

This dashboard is for educational and research purposes only. Stock market predictions are not guaranteed and should not be used as the sole basis for investment decisions. Always consult with a financial advisor before making investment decisions.
