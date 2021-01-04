---
title: "Structured Credit Analysis"
excerpt: "A set of analytical algorithms to forecast the cash flow of consumer loan-backed securities. <br/><img src='/images/ABS image.png' style='zoom:100%'>"
collection: portfolio
---

I wrote this memo in my first year as an alternative credit analyst, when I initiated the investment research of subordinate/equity tranche of consumer loan-bakced securities. My writing and coding were a bit immature in my early career. I plan to restructure my script the next time I work on this asset class.

Investing in consumer loan-backed securities require intensive statistical modelling and coding, especially if we are investing in the subordinate/equity tranches. Each security contains tens of thousands of consumer loans, and the performance of these assets follow the Law of Big Number. We need to estimate the probability distribution of default times and prepayment times. David Li, a Wall Street quant veteran, borrowed a statistical model, the Survival Analysis, from biostatistics to model the defaults and prepayments of each loan in the underlying asset pool. Furthermore, he proposed using Copula method to model the correlation among assets, e.g. mortgages issued in the same arear are all affected by the same housing price.

In this document, I outlined how I used these quantitative tools to analyze and forecast cash flows for consumer loans. I developed the first algorithm of such kind in China's capital market and I was among the first investors to tap the water in the equity tranche investment in China.


[Click to view my report](http://hoagiet.github.io/files/Investment Analysis of Structured Credit.pdf){:target="_blank"}

