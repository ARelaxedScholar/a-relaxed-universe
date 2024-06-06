---
{"dg-publish":true,"permalink":"/1-cosmos/test-on-significance-of-model-crucial-to-know-but-in-general-we-know-that-our-model-is-significant/"}
---

202405202250
Status: #idea
Tags: [[1. Cosmos/Hypothesis Testing in Multiple Linear Regression\|Hypothesis Testing in Multiple Linear Regression]]
## Test on Significance of Model (Crucial to know, but in general we know that our model is significant.)
We use [[1. Cosmos/Analysis of Variance (ANOVA)\|Analysis of Variance (ANOVA)]] to check the significance of our regression model.
[[1. Cosmos/Analysis of Variance (ANOVA)\|Analysis of Variance (ANOVA)]] in the context of [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]] will check if there is any linear relationship between the response and any of the regressor variables.

In other words it checks the following 
$H_0: \beta_1 = \dots = \beta_k = 0$ 
$H_1: \text{at least one of the cited coefficients has a positive slope}$
equivalently
$H_1 : \beta_j \ne 0 \text{, for some} j \ne j$ 

We're literally just doing [[1. Cosmos/Analysis of Variance (ANOVA)\|Analysis of Variance (ANOVA)]], so like in it we reject if our null hypothesis if our $F$ statistic is bigger than the $F_\alpha$ statistic for a given confidence level $\alpha$.

*Read the following screen capture and make sure you understand it, this contains everything you need to know
![Pasted image 20240518203351.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518203351.png)
![Pasted image 20240518203541.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518203541.png)

## References
[Video from Which The Screencaps Originate](https://www.youtube.com/watch?v=4jTeyIc9bVA&list=PLbMVogVj5nJSpj5sl-8tdKARg1lw2wEa-&index=7)
