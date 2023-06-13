# sp500_backtesting_analysis
Do mean reversion and/or trend following strategies work better than buy and hold w/ the S&amp;P 500? 

![plot](/img/download-1.png)

## Summary
I was curious to see if trend following and/or mean reversion strategies outperformed buy and hold with the S&P 500. I repurposed some backtesting scripts that I had written for cryptocurrency (https://github.com/hansenrhan/crypto_backtesting_analysis). The analyses were ran assuming 0 trading fees, but did apply a 30% tax each year if the strategy was profitable that year (since a major advantage of buy and hold is no taxes except when selling). The scripts also assume fractional shares as needed (which isn't quite realistic, but is a carryover from cryptocurrency backtesting). 

I looked at hourly data from the past two years using the yfinance library (since hourly data further past than that is not readily available). It would be interesting to look at that in the future.

I looked at four strategies: Mean Reversion w/ Shorting, Mean Reversion w/o Shorting, SMA Crossover w/ Shorting and SMA Crossover w/o Shorting. SMA Crossover strategies performed much higher across the board than Mean Reversion strategies, and only SMA Crossover w/ Shorting beat S&P 500 buy and hold in more than 50% of the runs. 

![plot](/img/comparison.png)



## Contents
```comparison_analysis.html```: R Markdown Analysis Output  
```comparison_analysis.Rmd```: R Markdown Analysis  
```mean_reversion_analysis.ipynb```: Mean Reversion Backtester Scripts  
```sma_crossover_analysis.ipynb```: Simple Moving Average (SMA) Crossover Scripts   
```run_output/```: Backtesting Results from Random Parameters

## Requirements
Python:
- yfinance
- seaborn
- matplotlib
- pandas
- numpy
- tqdm  

R:
- tidyverse
- ggpubr