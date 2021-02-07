---
title: "Structured Credit Analysis"
excerpt: "A set of analytical algorithms to forecast the cash flow of consumer loan-backed securities. <br/><img src='/images/ABS image.png' style='zoom:80%'>"
collection: portfolio
---

I wrote this memo in my first year as an alternative credit analyst, when I initiated the investment research of subordinate/equity tranche of consumer loan-bakced securities. My writing and coding were a bit immature in my early career when I was switching from R to Python. A more concise and more efficient version is coming soon.

Investing in consumer loan-backed securities requires intensive statistical modelling and coding, especially if we are investing in the subordinate/equity tranches. Each security contains tens of thousands of consumer loans, and the performance of these assets follow the Law of Big Number. We need to estimate the probability distribution of default times and prepayment times. David Li, a Wall Street quant veteran, borrowed a statistical model, the Survival Analysis, from biostatistics to model the defaults and prepayments of each loan in the underlying asset pool. Furthermore, he proposed using Copula method to model the correlation among assets, e.g. mortgages issued in the same arear are all affected by the same housing price. Building on Li's work, I further developed this method to incorporate static pool data and provided a better estimate of the hazard rate function, a critical component of the model.

In this document, I outlined how I used these quantitative tools to analyze and forecast cash flows for consumer loans.


[Click to view my report](http://hoagiet.github.io/files/Investment Analysis of Structured Credit.pdf){:target="_blank"}

[Click to view sample code](https://github.com/HoagieT/Structured-Credit-Analysis){:target="_blank"}

