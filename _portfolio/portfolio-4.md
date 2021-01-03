---
title: "Statistical Arbitrage Trading"
excerpt: "A statistical arbitrage trading strategy based on stochastic spread model. <br/><img src='/images/Stochastic Spread image.png' style='zoom:100%'>"
collection: portfolio
---


This project implements the framework described in "[Pairs Trading](http://stat.wharton.upenn.edu/~steele/Courses/434/434Context/PairsTrading/PairsTradingQFin05.pdf)" by Elliott et al.
The model is a statistical arbitrage algorithm based on mean reversion stochastic process and Kalman Filter. When implemented in China's interest rate futures and commodity futures, the model generates stable and significant returns. 


A chart for trading indicator is also designed in this project.

<br/><img src='/images/Stochastic Spread image.png' style='zoom:65%'>

**Chart Notes:** 
1. Red line represents the priori Kalman Filter prediction, i.e. the fair value of spreads.
2. Black line represents the observed spreads calculated with close price each day.
3. Blue area represents trading threshold, trade is triggered when black line breaks out of blue area.



[Click to view my model [Python]](https://github.com/HoagieT/Stochastic-Spread-Trading)
