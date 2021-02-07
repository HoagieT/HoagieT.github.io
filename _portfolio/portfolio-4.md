---
title: "Statistical Arbitrage Trading"
excerpt: "A statistical arbitrage trading strategy based on stochastic spread model. <br/><img src='/images/TradingRule.png' style='zoom:60%'>"
collection: portfolio
---


This project implements the framework described in "[Pairs Trading](http://stat.wharton.upenn.edu/~steele/Courses/434/434Context/PairsTrading/PairsTradingQFin05.pdf)" by Elliott et al.
The model is a statistical arbitrage algorithm based on mean reversion stochastic process and Kalman Filter. When implemented in China's treasury futures and commodity futures, the model generates stable and significant returns.


To make this strategy easier to illustrate, I made a chart for the trading indicators.

<br/><img src='/images/TradingRule.png' style='zoom:80%'>

**Chart Notes:** 
1. The black line represents the actual value of the commodity combination through time
2. The red line represents the fair value as calculated using the Kalman Filter for the commodity combination through time
3. The green line represents the long and short positions taken in the combination through time.
4. The blue band represents the trading threshold and the yellow band represents the close threshold.

Note that actual value being significantly less than the computed fair value coincides with buying the combination next period, while actual value being significantly more than the computed fair value coincides with selling the combination next period

**Trading rules:** 
1. Open a reverse position if the black line breaks out of the blue area.
2. Hold the position and wait for the black line to reverse to the red line.
3. Close the position when the black line touches the red line.


[Click to view my model [Python]](https://github.com/HoagieT/Stochastic-Spread-Trading){:target="_blank"}
