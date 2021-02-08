---
title: "Economic Forecasting with Factor Augmented Vector Autoregression"
excerpt: "An economic forecasting technique based on factor-augmented vector autoregression and incorporates big data. <br/><img src='/images/FAVAR image.png' style='zoom:100%'>"
collection: portfolio
---

I used a factor augmented vector autoregression (FAVAR) model to forecast copper price. FAVAR was first developed by Bernanke, Boivin and Eliasz (2004) to estimate the impact of monetary policy. Vanguard later applied this model to create the Vanguard Capital Market Model to forecast asset prices. Plese refer to https://www.nber.org/system/files/working_papers/w10220/w10220.pdf for detailed explaination of the model.

The mechanism is simple: the math behind FAVAR and classic VAR are the same. But unlike VAR, which can only take a few variables, FAVAR can incorporate a very large data set and reduce them to a few factors using principal component analysis.

Principal component analysis is an algorithm that finds a few common factors that can explain the most variation in the underlying data. It is like taking a two-dimensional photo for a three-dimentinal person. We can take the photo from many angles. Some angles can clearly identify the person, e.g. the front anglge, and others lose a lot of critical information, e.g. the back angle. Principal component analysis is an algorithm that finds the best shooting angle when we take a x-dimentional photo for a N-dimentional data set (x<<N).

Then, we combine variables of interest and the common factors to run the classical VAR regression. With this framework, we can include as many variables as possible and can even expand the model to a big data setting. To assess the impact of certain economic shocks, we can simply look at the impact reponse funcation.

The model also allows us to impose restrictions on the factors. Some economic indicators move synchronously with copper price, others lead or lag copper price movement. To implement this identification scheme, it is useful to define two categories of variables, “slow-moving” and “fast-moving”. A “slow-moving” variable is one that is largely predetermined as of the current period, while a “fast-moving” variable – think of an asset price – is highly sensitive to contemporaneous economic news or shocks.


[Click to view my model [Python]](https://github.com/HoagieT/Factor-Augmented-Vector-Autoregression){:target="_blank"}
