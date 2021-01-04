---
title: "Nowcast Model"
excerpt: "The Nowcast Model I wrote for forecasting near-term inflation data. <br/><img src='/images/Nowcast image.png' style='zoom:50%'>"
collection: portfolio
---

Nowcast Model was first developed by the US Federal Reserve. This model was developed to solve the problem described below. 

Since monthly data are usually released with a lag, sometimes so long as three weeks, the reconstruction of current-month inflation and other key variables is an important task for central banks. Financial authorities devote a considerable amount of resources to figuring out the current economic status and so should investment analysts.

To derive the monthly inflation data from multiple categories of price data, one may quickly turn to ordinary least squares (OLS) regressions. But OLS is unreliable in this scenario for three reasons. First, there are many kinds of industrial products, and throwing them all into a regression model will lead to multiple collinearity problems. If only applying the model to a few industrial products, then there is a lot of information going to waste. Second, inflation is a monthly data; while most of the prices are released daily or weekly. Linear regression cannot be directly performed on variables with different frequencies. Third, regression requires complete data, but at the time when we estimate CPI or PPI, the data set may have some null values.

So, we hope to find a way to: 1. effectively make use of as much industrial product price information as possible; 2. update monthly inflation forecasts based on weekly data flow; 3. allow for an incomplete data set and improve the prediction accuracy as the null values are gradually released. That is the Nowcast Model.

Nowcast model first reduce a large data set to a few common factors using Principal Component Analysis (PCA). Then, we run Structural VAR adn Kalman Filter on the common factors to predict the factors in the near term. If a variable is unavailable at a certain time point, Kalman Filter will not give any weight to this variable at that time point. In this way, even if part of the data set is missing, we can still calculate the factors and then use the factors to reversely derive the missing data. This is the core principle of the Nowcast technique.


[Click to view my Nowcast Model [Python]](https://github.com/HoagieT/Inflation-Nowcast-Models){:target="_blank"}
