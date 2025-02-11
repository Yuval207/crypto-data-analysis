# Cryptocurrency Live Data Fetcher and Analyzer

## Project Overview
This project automates the process of fetching, analyzing, and storing live cryptocurrency data for the top 50 cryptocurrencies by market capitalization. It continuously updates an Excel sheet with the latest data every five minutes, providing real-time insights.

## Features
- **Fetch Live Data:** Uses the CoinGecko API to retrieve cryptocurrency details such as price, market capitalization, and 24-hour price changes.
- **Data Analysis:**
  - Identifies the top 5 cryptocurrencies by market capitalization.
  - Computes the average price of the top 50 cryptocurrencies.
  - Determines the highest and lowest 24-hour percentage price changes.
- **Live Excel Updates:**
  - Saves the data in an Excel file (`crypto_live_data.xlsx`).
  - Updates every 5 minutes automatically.
- **Error Handling:**
  - Manages API rate limits.
  - Handles missing or corrupted Excel files.

## Technologies Used
- **Python**
- **APIs:** CoinGecko API
- **Libraries:**
  - `requests` - For API calls
  - `pandas` - For data analysis
  - `openpyxl` - For handling Excel files
  - `time` - For scheduling updates

## Installation
### Prerequisites
Ensure you have Python installed on your system. You can install the required dependencies using:
```sh
pip install requests pandas openpyxl
```

## Usage
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/crypto-live-analyzer.git
   cd crypto-live-analyzer
   ```
2. Run the script:
   ```sh
   python crypto_data_fetcher.py
   ```
3. The script will automatically update the Excel file (`crypto_live_data.xlsx`) every 5 minutes.

## File Structure
```
crypto-live-analyzer/
│── crypto_data_fetcher.py  # Main Python script
│── crypto_live_data.xlsx   # Excel file with live updates
│── README.md               # Documentation
```

## API Details
- **Source:** CoinGecko API (`https://api.coingecko.com/api/v3/coins/markets`)
- **Parameters Used:**
  - `vs_currency`: USD
  - `order`: market_cap_desc
  - `per_page`: 50
  - `page`: 1
  - `sparkline`: False

## Challenges & Solutions
- **Handling API Rate Limits:** Optimized request frequency to 5-minute intervals.
- **Ensuring File Integrity:** Automatically creates a new Excel file if missing or corrupted.
- **Data Accuracy:** Fetches data in real-time to maintain accuracy.



