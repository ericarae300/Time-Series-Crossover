# Time-Series-Crossover
Time Series Crossover Strategy - Portfolio of 10 stocks - Created in Jupyter Notebook with Python. 
Introduction: 

In this Time Series Crossover Notebook, I perform a detailed analysis of a portfolio consisting of 10 stocks with typical positive long-term returns using a time series crossover strategy. I include calculations for daily returns, cumulative returns, drawdowns, and other performance metrics. The goal of this analysis is to examine the historical performance of this portfolio, as well as provide insights to the risks and patterns involved in future investment decisions.  

 

Data Overview:  

Stocks Analyzed: Tesla (TSLA), Nvidia (NVDA), First Solar (FSLR), Boston Scientific (BSX), Medpace Holdings (MEDP), Bilibili (BILI), Aurora Innovation (AUR), Airbus SE (AIR), Autodesk (ADSK), Taiwan Semiconductor Manufacturing (TSM).  

Data Source: Yahoo Finance data extracted using the yfinance package.  

Time Period: 01/01/2010 through 12/01/2024.  

Frequency: Daily 

Data Columns: The data contains the following columns constructed in various data frames throughout the notebook: 

SMA_50 and SMA_200: Simple moving averages for 50 days and 200 days. 

signal: The buy sell signal  

log_returns: Logarithmic returns for each stock.  

strategy: Returns for each stock implementing the strategy.  

portfolio_log_returns: Logarithmic returns for the portfolio of stocks. 

cumulative_returns: Cumulative returns for the portfolio of stocks. 

rolling_volatility: Volatility of the portfolio rolling by date progression. 

cumulative_log_returns: Cumulative logarithmic returns for the portfolio.  

rolling_max: Maximum recorded return of the portfolio rolling by date progression.  

drawdown: Drawdown value of the portfolio – difference between cumulative logarithmic returns on the portfolio and the rolling maximum recorded return on the portfolio on each trading day.  

 

Methodology:  

The following analysis steps were performed:  

Downloaded 10 stocks to form my portfolio of stocks from Yahoo Finance.  

Cleaned the data to remove all original data columns aside from the closing value of each stock at the end of each trading day. Removed NaN values from the data set to omit non-trading days due to holidays and weekends.  

Calculated the daily returns for each stock and compared the correlation between the returns by using a correlation matrix and displaying correlation in a heatmap.  

Calculated the 50-day and 200-day simple moving averages (SMA) for each stock. Created a new data frame to store this data inside.  

Developed a signaling system to signal either a buy or sell position for each new trading day. If the 50-day SMA was greater than the 200-day SMA this will generate a 1, signaling a buy – otherwise, 0 signals a sell.  

Calculated the daily logarithmic returns for each stock and added them into a data frame. 

Calculated the returns for each stock by implementing the SMA signaling strategy – multiplied the daily logarithmic returns by the previous day’s signal.  

Construct a new data frame by equally weighting each of the 10 stocks and recording the total portfolio logarithmic returns on each date. Then calculated and added the cumulative returns, rolling volatility, cumulative log returns, rolling maximum return, and drawdown value into their individual columns for each date.  

Found the maximum drawdown value and date, average drawdown value, annualized volatility, annualized return, and the annualized Sharpe ratio to construct risk metrics.  

Visualized data patterns by generating plots for the cumulative portfolio returns, log returns, drawdown value, and rolling volatility over time.  

 

Results:  

The following results were derived from the analysis:  

Portfolio Returns: There was an overall positive return on this portfolio analyzing dates from 01/01/2010 to 12/01/2024. Over this near 15-year period the cumulative returns were determined to be approximately 199.324%, while the cumulative logarithmic returns were determined to be approximately 109.636%. Cumulative logarithmic returns were calculated in addition to simple cumulative returns due to the infinite support, suppression of large positive returns, and emphasis of large negative returns that result from the logarithmic function. This results in more symmetric results when compared to the simple cumulative return calculation.  

Maximum Drawdown: The maximum drawdown value was observed to be approximately 0.3604. This drawdown value occurred on 03/18/2020 and might be attributed in part to the stock market crash of 2020 following the outbreak of COVID-19 pandemic, which had its largest impact on the overall market on 03/09/2020, 03/12/2020, and 03/16/2020. “Prior to the 2020 crash, the Dow reached a record high of 29,551.42” on 02/12/202, which explains the substantial drawdown that occurred in the following month (https://www.thebalancemoney.com/fundamentals-of-the-2020-market-crash-4799950). The maximum drawdown can be interpreted as the portfolio dropping 36.04% from its highest value before recovering.  

Volatility: The annualized volatility came out to approximately 18.95%, determined using standard deviation. Thus, the returns on this portfolio deviated from its average returns by 18.95%. I downloaded data from the FRED that showed CBOE S&P 500 3-Month Volatility Index (VXVCLS). This reported the S&P 500's market expectations of 3-month volatility - given through annualized implied volatility. Taken from the same 15-year period that I used for the stock data downloaded from Yahoo Finance; the average 3-month annualized implied volatility was approximately 20.29%. Thus, using my strategy and 10 stock portfolio, I was able to create a portfolio with slightly improved volatility compared to this S&P 500 index volatility. I also calculated an annualized Sharpe ratio to analyze volatility. The annualized Sharpe ratio I found was approximately 0.7894. Because this value is below 1, this is not optimal, as I would have preferred to see a risk-adjusted return of 1 or higher. The Sharpe ratio measures the level of return obtained based on the level of risk associated with the portfolio, and a larger Sharpe ratio (usually of at least 1) would signal a good level of return when compared to the risk of the portfolio. However, a ratio of 0.7894 is relatively close to 1, and it is a positive value, which means that the portfolio is generating a positive return overall. To improve this ratio, it would be a good idea to try and select some alternative stocks with either higher returns or lower risk.  

 

Usage:  

To reproduce or modify this strategy and analysis with your own dataset you may:  

Clone this repo or download the notebook. 

Install the necessary dependencies (documented below).  

Modify the stock symbols and/or dates to align with your personal analysis needs.  

Please cite my code when copied directly or when used for purposes other than personal analysis.  

 

Dependencies: 

This notebook utilizes the following Python libraries:  

pandas 

numpy 

matplotlib 

yfinance 

 

 

  
