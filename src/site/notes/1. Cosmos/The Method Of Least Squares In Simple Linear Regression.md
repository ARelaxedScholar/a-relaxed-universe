---
{"dg-publish":true,"permalink":"/1-cosmos/the-method-of-least-squares-in-simple-linear-regression/","created":"2024-08-31T23:47:13.892-04:00","updated":"2024-06-14T09:50:51.596-04:00"}
---

202405202143
Status: #idea
Tags: [[Regression Analysis\|Regression Analysis]]
# The Method Of Least Squares In Simple Linear Regression

![Pasted image 20240503141814.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240503141814.png)
*The above gives the derived formula for the two estimators. Try to remember the formula for Y_bar and X_bar and all the other terms.*
![Pasted image 20240614094953.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240614094953.png)
*I paste this here, because while I realize showing unbiasedness is almost trivial if you take the general case of [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]], these formulas make the proof for unbiasedness basically one liners.*
The idea of the Method of Least Squares is something you should already be keenly aware of, since it's a loss function that is used a lot in [[1. Cosmos/Machine Learning\|Machine Learning]]. But the idea is to take the difference between all the errors and sum them together. The issue is that since some differences will positive, and others would be negative, simply summing them would lead to cancellation of them.

Therefore there are two ways to proceed forward, either we take the absolute value of the errors and proceed what is called as [[Mean Absolute Error (L1 Loss)\|Mean Absolute Error (L1 Loss)]] which is a sensible method that is used quite often in machine learning models because of its simplicity of interpretation, and the its resistance to outliers or you use use [[Mean Squared Error (L2 Loss)\|Mean Squared Error (L2 Loss)]]
which is quite sensible to outliers.

You might be surprised to learn that [[Mean Squared Error (L2 Loss)\|Mean Squared Error (L2 Loss)]] is the defacto method we use in [[1. Cosmos/Linear Regression\|Linear Regression]] problems in [[Statistics\|Statistics]] and [[Probability\|Probability]]. Why?

Because, by taking the derivative of our summations of squared errors with respect to $\beta_0$ the constant term (here represented as $b$) and $\beta_1$ the slope (here represented as $m$) it is possible to solve for the values, and to get these terms in term of equations which by [[Gauss-Malkov Theorem\|Gauss-Malkov Theorem]] will be unbiased estimators which minimise the variance for that term.

If you remember your calculus, you likely already know why we wouldn't use [[Mean Absolute Error (L1 Loss)\|Mean Absolute Error (L1 Loss)]] in an algorithm that makes use of derivatives. But the point is, that the absolute value function is not differentiable at $0$. Try to prove it using [[Fundamental Theorem of Calculus\|Fundamental Theorem of Calculus]].

If you wonder how [[Mean Absolute Error (L1 Loss)\|Mean Absolute Error (L1 Loss)]] can be used in [[1. Cosmos/Machine Learning\|Machine Learning]] even though so many models use [[Stochastic Gradient Descent (SGD)\|Stochastic Gradient Descent (SGD)]] (a differentiation based algorithm) as an optimiser, the simple answer is that while [[Mean Absolute Error (L1 Loss)\|Mean Absolute Error (L1 Loss)]] does not have a gradient at $0$ it does have a [[Subgradient\|Subgradient]]. For more indepth explanation, please consult this discussion with the AI :[Short ChatGPT Convo on Simple Linear Regression](https://chat.openai.com/share/14e53b74-ad9a-459c-95fb-7f3972990c64)



## References
