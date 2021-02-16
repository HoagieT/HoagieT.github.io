---
title: "Nowcast Model"
excerpt: "The Nowcast Model I wrote for forecasting near-term inflation data. <br/><img src='/images/Nowcast image.png' style='zoom:50%'>"
collection: portfolio
---

Nowcast Model was first developed by the US Federal Reserve. This model was developed to solve the problem described below. 

<br/><img src='/images/Nowcast image-2.png' style='zoom:100%'>

Since monthly data are usually released with a lag, sometimes so long as three weeks, the reconstruction of current-month inflation and other key variables is an important task for central banks. Financial authorities devote a considerable amount of resources to figuring out the current economic status and so should investment analysts.

To derive the monthly inflation data from multiple categories of price data, one may quickly turn to ordinary least squares (OLS) regressions. But OLS is unreliable in this scenario for three reasons. First, there are many kinds of industrial products, and throwing them all into a regression model will lead to multiple collinearity problems. If only applying the model to a few industrial products, a lot of information is wasted. Second, inflation index is a monthly data; while most of the industrial product prices are released daily or weekly. Linear regression cannot be directly performed on variables with different frequencies. Third, regression requires complete data, but at the time when we estimate CPI or PPI, the data set may have some null values, i.e. the data set is unbalanced.

So, we hope to find a way to: 1. effectively make use of as much industrial product price information as possible; 2. update monthly inflation forecasts based on weekly data flow; 3. allow for an incomplete data set and improve the prediction accuracy as the null values are gradually released. That is the Nowcast Model.

To perform a nowcast, we first reduce a large data set to a few common factors using Principal Component Analysis (PCA). Then, we run Structural VAR and Kalman Filter on the common factors to predict the factors to the next month. If a variable is unavailable at a certain time point, Kalman Filter will not give any weight to this variable at that time point. In this way, even if part of the data set is missing, we can still calculate the factors and then use the factors to reversely derive the missing data. This is the core principle of the Nowcast technique.

# What can we use it for?

Nowcast method can be used in any time-to-event analysis. On 31 May 2020, my Nowcast Model predicted that M/M growth of CPI in May was -0.5%, and the M/M growth of PPI in May was -0.22%. The respective predicted Y/Y growth rates in May are 2.6% and -3.5%. At the time, market expectation for the Y/Y growth rate of CPI and PPI were 3.02% and -3.03%. Because the Nowcast predictions were significantly lower than market expectations, I advised portfolio managers to long treasury bond future at market opening on 10 June, the day when the May inflation data is released. Specifically, I advised them to long the TS2009 contract, which delivers 2Y treasury bonds on 20 September 2009, because inflation surprises have a stronger effect on short-term treasury bonds. The future market opens at 9:15 a.m., and the inflation data is released around 9:30 a.m. The actual inflation data released at 9:30 a.m. were 2.4% for CPI and -3.7% for PPI, much lower than market expectation and slightly lower than the Nowcast prediction. As is shown in the chart below, the treasury future rose to intra-day highest point quickly after the inflation data was released.

<br/><img src='/images/Inflation Arbitrage.png' style='zoom:80%'>

Note: The arrow points to the moment when inflation data was released. After the inflation data was released, treasury future price quickly rose to intra-day highest point in six minutes.

[Click to view my Nowcast Model [Python]](https://github.com/HoagieT/Inflation-Nowcast-Model){:target="_blank"}
