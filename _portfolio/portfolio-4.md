---
title: "Statistical Arbitrage Trading"
excerpt: "A statistical arbitrage trading strategy based on stochastic spread model. <br/><img src='/images/Stochastic Spread image.png' style='zoom:100%'>"
collection: portfolio
---


This project implements the framework described in "[Pairs Trading](http://stat.wharton.upenn.edu/~steele/Courses/434/434Context/PairsTrading/PairsTradingQFin05.pdf)" by Elliott et al.
The model is a statistical arbitrage algorithm based on mean reversion stochastic process and Kalman Filter. When implemented in China's treasury futures and commodity futures, the model generates stable and significant returns.


To make this strategy easier to illustrate, I made a chart for the trading indicators.

<br/><img src='/images/Combo4#25.png' style='zoom:100%'>

**Chart Notes:** 
1. Red line represents the priori Kalman Filter prediction, i.e. the fair value of price spread.
2. Black line represents the observed spreads calculated with close price each day.
3. Blue area represents trading threshold, trade is triggered when black line breaks out of blue area.

**Trading rules:** 
1. Open a reverse position if the black line breaks out of the blue area.
2. Hold the position and wait for the black line to reverse to the red line.
3. Close the position when the black line touches the red line.


[Click to view my model [Python]](https://github.com/HoagieT/Stochastic-Spread-Trading){:target="_blank"}
