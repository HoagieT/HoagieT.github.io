---
title: "Stochastic Spread Trading"
excerpt: "A statistical arbitrage trading strategy based on stochastic spread model. <br/><img src='/images/TradingRule.png' style='zoom:60%'>"
collection: portfolio
---

This project proposed a quantitative rules-based strategy, which we term the Divergent Scouter, that trades combinations of cointegrated commodity futures and capitalizes during temporary deviations from the stationarity of their relationship. Specifically, the strategy first identifies linear combinations of commodity futures that form a stationary price series; we call such a stationary price series the spread of a given combination. Whenever this combination spread deviates from its computed fair value, we open a position (going long and short the appropriate futures as dictated by the linear combination coefficients) betting on a reversal back to the spread’s fair value. We close the position and realize a profit once the spread reverses.


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
3. Close the position when the black line converges to the yellow area.


The code is not made public for this project.
