# ðŸš€ Real-Time Cryptocurrency Price Analysis and Visualization Pipeline

## ðŸ“‹ Project Overview

This project implements a comprehensive real-time cryptocurrency data collection and analysis pipeline using Python. It fetches live cryptocurrency prices from the CoinMarketCap API, processes the data with pandas, and creates interactive visualizations to track price movements and trends.

## ðŸŒŸ Key Features

### ðŸ“Š Real-Time Data Collection
- **Live API Integration**: Connects to CoinMarketCap Pro API for real-time cryptocurrency data
- **Automated Data Fetching**: Collects data at customizable intervals (1-5 minutes)
- **Multi-Currency Support**: Tracks top 15 cryptocurrencies including Bitcoin, Ethereum, and more
- **Dual Storage**: Automatically saves data to both local CSV files and network drives

### ðŸ“ˆ Advanced Analytics
- **Price Movement Tracking**: Real-time monitoring of price changes with percentage calculations
- **Historical Trend Analysis**: Analyzes 1h, 24h, 7d, 30d, 60d, and 90d percentage changes
- **Statistical Aggregation**: Groups and summarizes data by cryptocurrency for trend identification

### ðŸŽ¨ Interactive Visualizations
- **Live Price Charts**: Real-time line plots showing Bitcoin price movements
- **Multi-Timeframe Analysis**: Categorical plots for comparing percentage changes across different time periods
- **Custom Chart Updates**: Automatic chart generation during data collection cycles
- **Professional Styling**: Uses Seaborn's darkgrid theme for polished visualizations

### âš¡ Quick Collection Mode
- **5-Minute Collection**: Rapid data gathering for immediate analysis
- **1-Minute Intervals**: High-frequency sampling for detailed price tracking
- **Live Progress Tracking**: Real-time updates showing collection progress and price changes
- **Automatic Chart Generation**: Charts update every 3 data points during collection

## ðŸ› ï¸ Technologies Used

### Core Libraries
- **pandas**: Data manipulation and analysis
- **requests**: HTTP requests for API communication
- **matplotlib**: Basic plotting functionality
- **seaborn**: Advanced statistical visualizations
- **json**: API response parsing

### APIs
- **CoinMarketCap Pro API**: Professional cryptocurrency data service

## ðŸš€ Getting Started

### Prerequisites
```python
pip install pandas requests matplotlib seaborn jupyter
```

### API Setup
1. Get a free API key from [CoinMarketCap Pro API](https://pro.coinmarketcap.com/api/v1)
2. Replace the API key in the headers configuration

### Quick Start
1. **Initialize the Environment**: Run cells 1-5 to set up imports and functions
2. **Import Visualization Libraries**: Execute cell 20 for plotting capabilities
3. **Load Quick Collection Function**: Run cell 24 to define the collection function
4. **Start Data Collection**: Execute cell 25 to begin real-time collection

## ðŸ“‹ Usage Examples

### Basic Data Collection
```python
# Collect Bitcoin data for 5 minutes at 1-minute intervals
quick_bitcoin_collection()
```

### Extended Collection
```python
# Collect data for 10 minutes at 2-minute intervals
quick_bitcoin_collection(duration_minutes=10, interval_minutes=2)

# Collect data for 30 minutes at 5-minute intervals  
quick_bitcoin_collection(duration_minutes=30, interval_minutes=5)
```

### Data Analysis
```python
# Load and analyze collected data
df_csv = pd.read_csv('crypto_data.csv')
bitcoin_data = df_csv[df_csv['name'] == 'Bitcoin']

# Generate price visualization
sns.lineplot(x='timestamp', y='quote.USD.price', data=bitcoin_data)
```

## ðŸ“ Project Structure

```
â”œâ”€â”€ Real-Time Cryptocurrency Price Analysis and Visualization Pipeline.ipynb
â”œâ”€â”€ crypto_data.csv                 # Local data storage
â”œâ”€â”€ M:\Data\Automating-Crypto-Website-API\API.csv  # Network backup
â””â”€â”€ README.md                       # This documentation
```

## ðŸ“Š Data Schema

### Raw API Data
- **id**: Unique cryptocurrency identifier
- **name**: Cryptocurrency name (e.g., "Bitcoin")
- **symbol**: Trading symbol (e.g., "BTC")
- **quote.USD.price**: Current price in USD
- **quote.USD.percent_change_1h**: 1-hour percentage change
- **quote.USD.percent_change_24h**: 24-hour percentage change
- **quote.USD.percent_change_7d**: 7-day percentage change
- **timestamp**: Data collection timestamp

### Processed Data
- Clean pandas DataFrames with normalized JSON structure
- Time-series data with consistent timestamp formatting
- Aggregated statistics for trend analysis

## ðŸŽ¯ Key Functions

### `api_runner()`
- Fetches live cryptocurrency data from CoinMarketCap API
- Processes and normalizes JSON responses
- Appends new data to existing DataFrame
- Saves data to multiple locations for redundancy

### `quick_bitcoin_collection(duration_minutes, interval_minutes)`
- Orchestrates real-time data collection cycles
- Provides live progress updates and price change tracking
- Generates intermediate charts during collection
- Creates comprehensive final visualization

## ðŸ“ˆ Visualization Features

### Real-Time Price Tracking
- Live Bitcoin price updates with change indicators (ðŸ“ˆðŸ“‰âž¡ï¸)
- Price range analysis with min/max values
- Percentage change calculations with directional indicators

### Statistical Analysis
- Multi-timeframe trend comparison (1h to 90d)
- Categorical plotting for cross-cryptocurrency analysis
- Time-series visualization with professional styling

## ðŸ”§ Configuration Options

### Collection Parameters
- **duration_minutes**: Total collection time (default: 5)
- **interval_minutes**: Time between collections (default: 1)
- **chart_update_frequency**: Chart generation interval (every 3 collections)

### Data Storage
- **Local CSV**: `crypto_data.csv` in working directory
- **Network Backup**: `M:\Data\Automating-Crypto-Website-API\API.csv`
- **Format**: CSV with timestamp and full cryptocurrency data

## ðŸš¨ Error Handling

- **API Connection Issues**: Graceful handling of network timeouts and connection errors
- **Missing Dependencies**: Clear error messages for import failures
- **Data Validation**: Robust DataFrame operations with existence checks
- **Storage Fallbacks**: Multiple save locations with error reporting

## ðŸ“Š Sample Output

### Live Collection Progress
```
ðŸš€ Quick Bitcoin Collection Starting!
â° Every 1 minutes for 5 minutes
ðŸ“Š Will collect 5 data points
ðŸ Finishing at: 04:10:31

ðŸ”„ Collection 1/5 at 04:05:31
ðŸ’° Bitcoin: $107,577.26
ðŸ“Š Total Bitcoin records: 1

ðŸ”„ Collection 2/5 at 04:06:32
ðŸ’° Bitcoin: $107,782.64
ðŸ“Š Total Bitcoin records: 2
ðŸ“ˆ Change: $+205.38 (+0.191%)
```

### Final Results
- **Price Range**: $107,577 - $107,803
- **Total Records**: 75 cryptocurrency entries
- **Bitcoin Data Points**: 5 time-series records
- **Visualizations**: 2 charts (intermediate + final)

## ðŸ™ Acknowledgments

- **CoinMarketCap**: For providing comprehensive cryptocurrency API data
- **Pandas Development Team**: For powerful data manipulation tools
- **Matplotlib/Seaborn**: For excellent visualization capabilities
- **Jupyter Project**: For interactive development environment


