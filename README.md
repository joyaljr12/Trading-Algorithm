# Trading-Algorithm
This project implements a backtesting strategy based on the Relative Strength Index (RSI) indicator. The strategy opens long positions when the RSI falls below 30 (oversold condition) and short positions when the RSI rises above 70 (overbought condition). The Average True Range (ATR) indicator sets the stop-loss and take-profit levels. 
Libraries and Data Retrieval
The project utilizes several Python libraries: 
 
•	‘yfinance’ for retrieving historical price data.
•	‘pandas’ for data manipulation.
•	‘numpy’ for numerical operations.
•	‘matplotlib’ for plotting.

Code Structure
The code is divided into the following sections:
1.	Data Preparation
i.	Data Retrieval: This section downloads historical stock data from Yahoo Finance using the yfinance library. The user can specify the stock symbol, timeframe, and the number of bars to retrieve.
ii.	Data Preprocessing: The retrieved data is pre-processed, and the required columns are selected and renamed.

2.	Indicators Calculation
i.	RSI Calculation: This section calculates the RSI indicator using the exponential moving average (EMA) method.
            RSI is calculated over a 14-period window:
i.1.	Compute gains and losses.
            RSI is calculated over a 14-period window:
i.1.	Compute gains and losses.
i.2.	 Calculate exponential moving averages for gains and losses.
i.3.	Compute the Relative Strength (RS).
i.4.	Derive RSI from RS.
 
ii.	ATR Calculation: This section calculates the Average True Range (ATR) indicator, which is used to set the stop-loss and take-profit levels. ATR is calculated over a 14-period window as the rolling mean of the range (high-low).
 
3.	Strategy LogiC
The strategy opens a position based on RSI values:
•	Buy when RSI < 30 (indicating oversold conditions).
•	Sell when RSI > 70 (indicating overbought conditions).
Positions are closed based on stop loss (SL) or take profit (TP) levels, set at 2 times the ATR away from the open price.
•	For oversold conditions (RSI < 30):
•	For overbought conditions (RSI > 70):
 
4.	Position and Strategy Classes
The Position class represents a single trade position, and the Strategy class defines the trading logic and manages the positions.
A ‘Position’ class was used to manage trade details
A ‘Strategy’ class encapsulated the trading logic
 
5.	Backtesting Methodology
The backtesting process is executed by creating an instance of the Strategy class and running the run method. This method iterates through the historical data, opens and closes positions based on the trading logic, and calculates each position's profit and loss (PnL).

