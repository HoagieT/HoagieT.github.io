---
title: "Value Investing Screening Model"
excerpt: "<br/><img src='/images/DEA image.png' style='zoom:40%'>"
collection: portfolio
---
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.11.1/katex.min.css">

In value investing, the first step is to look for potentially undervalued stocks. I borrowed an analytical algorithm from operational research, the Data Envelopment Analysis (DEA), to help me find companies whose valuation comps are not warranted by their financial statements.
DEA is a method that enables us to compare and rank records based on their features without making any prior assumptions about the importance or weights of the features. Each record/stock has M inputs that measure the financial performances, and N outputs that measure the company’s valuation.

<img src="https://latex.codecogs.com/gif.latex?E_{i}=\frac{\sum_{r=1}^{N}u_{r,i}y_{r,i}}{\sum_{s=1}^{M}v_{s,i}x_{r,i}}" title="E_{i}=\frac{\sum_{r=1}^{N}u_{r,i}y_{r,i}}{\sum_{s=1}^{M}v_{s,i}x_{r,i}}" /></a>

where, E is the efficiency of stock i, u and v are the weights of each output and input of the record. Then the problem of finding the best weights for a particular record i can be formulated as follows:
maximize h=(∑_(r=1)^(r=N)▒〖u_(r,i) y_(r,i) 〗)/(∑_(s=1)^(s=M)▒〖v_(s,i) x_(s,i) 〗)
subject to  (∑_(r=1)^(r=N)▒〖u_(r,i) y_(r,j) 〗)/(∑_(s=1)^(s=M)▒〖v_(s,i) x_(s,j) 〗)≤1 for every j record
u_(r,i),v_(s,i)≥0
The above optimization problem can be solved with Linear Dynamic Programming. The h in the first equation is called efficiency. A low efficiency indicates that the company might be undervalued. To apply this algorithm to assist value investing, I used each company’s financial statistics as inputs and valuation comps as outputs (see table below).


[Click to view my stock screening model [Python]](https://github.com/HoagieT/Stock-Screening-Model-Based-On-Data-Envelopment-Analysis)
