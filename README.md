# Algorithmic-Trading

## Project Title
Comparative Analysis of Trading Algorithms via Amazon Stock

## Team Members
Indrajith Senevirathne, Shishir Suman, and Sujit Subhash

## Project Description/outline
Four (4) parts to the project:
1. Dual Simple Moving Average (SMA) Crossover Strategy
2. Dual Exponentially Weighted Moving Average (EWM) Crossover Strategy 
3. Algorithmic Trading Analysis using a combination of two Trading Indicators: Stochastic Oscillator and Simple Moving Average
4. Machine Learning Models - classification problem via Support Vector Machine (SVM), Random Forest (RF), and Gradient Boost (GB)

## Research questions to answer
The goal of this Study is to define and comparatively study multiple Algorithmic Trading Models and generate signals, and buy/sell strategies.
Further, we ran Machine Learning models to predict the efficiency of trading decisions.

## Datasets to be used
Amazon Stock (AMZN) market data using Alpaca API daily closing price for 5 years (9/15/2016 - 9/15/2021).

### Part 1 - Dual Simple Moving Average (SMA) Crossover Strategy
Extracted daily closing price and used. 4-day moving average was selected for sma-fast. 24-day moving average was selected for sma-slow. Dual SMA crossover signal generated and then it was used to generate buy/sell signals. Back testing and the transaction table was generated. Intotal with the time frame 23 transactions were recorderd. The metrics were generated to access the effectiveness.

### Part 2 - Dual Exponentially Weighted Moving Average (EWM) Crossover Strategy
Extracted daily closing price and used. 4-day moving average was selected for sma-fast. 24-day moving average was selected for sma-slow. Dual EWM crossover signal generated and then it was used to generate buy/sell signals. Back testing and the transaction table was generated. Intotal with the time frame 25 transactions were recorderd. The metrics were generated to access the effectiveness.

#### Comparison - 
Between the SMA and EWM dual crossover strategies, EWM dual crossover strategy has a reduced annual return, increased cumulative returns, decreased volatility, increased Sharpe ratio, and increased Sortino ratio. This strategy had more transactions (23 to 25, not shown) i.e., likely incur marginally increased cost.  
Bottomline: EWM Dual Crossover Strategy is marginally superior.

### Part 3 - Algorithmic Trading Analysis using a combination of two Trading Indicators: Stochastic Oscillator and Simple Moving Average  

Create Stochastic Oscillator Model
1. Define %K Line number of periods
2. Calculate K Line
3. Define %D Line number of Periods
4. Calculate %D Line
5. Create Trading Signal
```
IF %K LINE < 20 AND %D LINE < 20 AND %K LINE < %D LINE => BUY
IF %K LINE > 80 AND %D LINE > 80 AND %K LINE > %D LINE => SELL
```

Add Simple Moving Average Trading Indicators  
1. Define Short Window and Calculate Fast Indicator  
2. Define Long Window and Calculate Slow Indicator  
3. Combine signals for Stochastic Oscillator, and Simple Moving Average using 'OR' operator  

Run the model and perform Backtesting to generate the following for model evaluation:  
1. Annual Returns  
2. Cumulative Returns  
3. Annualized Volatility  
4. Sharpe Ratio  
5. Sortino Ratio  

Run Parameter Sweep for the combined Model  
For each combination of Parameters for the two models, run the full Trading Analysis and Backtesting to find out the Param Set which has the best Sharpe Ratio, and Cumulative Returns  
    
Refine The model using the Param set determined by the Param sweep exercise  


### Part 4 - Machine Learning Models - classification problem via Support Vector Machine (SVM), Random Forest (RF), and Gradient Boost (GB) 
Considering all three predictive models Random Forrest showed the best accuracy score (0.78) while the worst was the Support Vector Machines model (0.65). All models show significant trading algorithm return gains compared to the actual gains. 

## Inputs
Data were read from Alpaca API for Amazon security closing prices. Extracted data was used to create the representative dataframes.

## Outputs
Outputs are given out as mentioned above on the terminal as calculated values, graphs, and explanations about the results.

## Remarks
Some implementations require selective decision making upon observing a metric: case in point when we attempt to implement Relative Strength Index (RSI) as the movements of index would result in sequential buy signals or sequential sell signals where a  user selects the point of entry or exit from the index.   
Parameter Sweep Exercise is costly from computation perspective. A high end GPU processor, mostly could based (AWS Sagemaker/Google Colab) could help to reduce the execution time. 
Future Studies can be done to improve the two trading indicator model by adding a third one, most likely Relative Strength Index (RSI), and an ability to pre-smooth the curve.

##  Bibliography/References

### Stochastic Oscillator:
https://medium.com/codex/algorithmic-trading-with-stochastic-oscillator-in-python-7e2bec49b60d  
https://www.metastock.com/customer/resources/taaz/?p=106  
### Dual Crossover SMA
https://www.investopedia.com/articles/active-trading/052014/how-use-moving-average-buy-stocks.asp
### Dual Crossover EWM
https://www.statology.org/exponential-moving-average-pandas/  
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.ewm.html  
### Sharpe Ratio
https://www.investopedia.com/terms/s/sharperatio.asp  
### Sortino Ratio
https://www.investopedia.com/terms/s/sortinoratio.asp  
https://therobusttrader.com/sortino-ratio/  






