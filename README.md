# VSVTrend Trading Strategy Library

## Project Overview

VSVTrend is a sophisticated trading strategy library for TradingView, designed to help traders implement a robust trend-following strategy using the Supertrend indicator. This strategy provides automated entry and exit points with configurable risk management parameters.

### Key Features
- Adaptive trend-following strategy
- Supertrend indicator integration
- Configurable take-profit and stop-loss percentages
- Strategy toggle functionality
- Supports both long and short trading positions

## Installation

### Prerequisites
- TradingView Pine Script v5
- Basic understanding of trading strategies and technical analysis

### Usage
1. Open TradingView Pine Editor
2. Create a new Pine Script
3. Copy and paste the contents of `VSVTrend.pine`
4. Compile and add to chart

## API Reference

### Strategy Inputs
- `show_strategy` (boolean): 
  - Enables/disables the entire trading strategy
  - Default: `true`

- `use_supertrend` (boolean):
  - Toggles Supertrend filter visualization
  - Default: `true`

- `atrPeriod` (integer):
  - Average True Range (ATR) calculation period
  - Default: `10`
  - Range: Any positive integer

- `factor` (float):
  - Multiplier for ATR in Supertrend calculation
  - Default: `3.0`
  - Range: Typically between 1.0 and 5.0

### Risk Management Inputs
- `sl` (float):
  - Stop-loss percentage
  - Default: `1.5%`
  - Input as decimal (e.g., 1.5 for 1.5%)

- `tp` (float):
  - Take-profit percentage
  - Default: `3.0%`
  - Input as decimal (e.g., 3.0 for 3.0%)

### Strategy Methods
- `strategy.entry()`: Enters long or short positions based on Supertrend direction
- `strategy.exit()`: Manages exit with predefined take-profit and stop-loss

## Repository Structure
- `VSVTrend.pine`: Main strategy implementation
- `LICENSE`: MIT License file
- `README.md`: Project documentation

## Example Usage

```pine
//@version=5
// Default configuration
strategy("VSVTrend Strategy", overlay=true)
```

## Contributing
Contributions are welcome! Please consider:
- Reporting bugs
- Suggesting improvements
- Submitting pull requests

When contributing:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a pull request

## License
This project is licensed under the MIT License. See `LICENSE` file for details.

## Disclaimer
Trading strategies involve financial risk. This library is for educational purposes and should not be considered financial advice. Always backtest and use proper risk management.