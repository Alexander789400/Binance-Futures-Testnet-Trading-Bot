# Binance-Futures-Testnet-Trading-Bot

A simplified Python trading bot that can place orders on **Binance USDT-M Futures Testnet** through a clean command-line interface.

This project was built as part of a Python Developer assignment and demonstrates:

- Market & Limit order placement  
- BUY and SELL support  
- Proper CLI input validation  
- Clean project structure (API layer + CLI layer)  
- Logging of requests/responses/errors into `bot.log`  
- Mock mode support (runs even without API keys)

---

##  Project Overview :

This bot allows users to place Futures orders on Binance Testnet using Python.

Supported order types:

-  MARKET Orders  
-  LIMIT Orders  
-  STOP-LIMIT Orders (Bonus)

The bot supports two modes:

###  Real Mode (With Binance API Keys)
- Places real orders on Binance Futures Testnet  
- Demonstrates correct Binance API integration  

###  Mock Mode (Without API Keys)
- Simulates order execution safely  
- Allows recruiters to run the project without credentials  
- Useful for offline testing and reproducibility  

---

##  Project Structure

binance_bot/
│
├── src/
│   ├── cli.py                 # Main CLI entry point
│
│   ├── api/
│   │   └── client.py          # Binance Futures client + Mock client
│
│   ├── orders/
│   │   ├── market.py          # Market order logic
│   │   ├── limit.py           # Limit order logic
│   │   └── stop_limit.py      # Stop-Limit order logic (bonus)
│
│   ├── utils/
│       ├── logger.py          # Logging configuration
│       └── validators.py      # Input validation helpers
│
├── bot.log                    # Request/response/error logs
├── requirements.txt           # Dependencies
└── README.md


Installation:

cd binance-bot

Install dependencies:

pip install -r requirements.txt

Running without API keys (Mock Mode):

Market Order:

python -m src.cli --mock --symbol BTCUSDT --side BUY --type MARKET --qty 0.01

Limit Order:

python -m src.cli --mock --symbol BTCUSDT --side SELL --type LIMIT --qty 0.01 --price 50000

Stop-Limit Order:

python -m src.cli --mock --symbol BTCUSDT --side BUY --type STOP_LIMIT --qty 0.01 --stop 48000 --price 48100

Running with API keys (Real Binance Testnet Mode):

Create API keys from:

https://testnet.binancefuture.com

Set keys in terminal (Windows CMD):

set BINANCE_API_KEY=your_api_key
set BINANCE_API_SECRET=your_secret_key

Run Market Order:

python -m src.cli --symbol BTCUSDT --side BUY --type MARKET --qty 0.01

Run Limit Order:

python -m src.cli --symbol BTCUSDT --side SELL --type LIMIT --qty 0.01 --price 50000

Logs:

All actions, API responses, and errors are saved in bot.log.

Deliverables Covered:

Market Orders
Limit Orders
BUY/SELL Support
Validation
Logging
Mock Mode
Bonus Stop-Limit Order

Author:

Alexander Roy

