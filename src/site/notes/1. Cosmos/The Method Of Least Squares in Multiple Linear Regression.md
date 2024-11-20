---
{"dg-publish":true,"permalink":"/1-cosmos/the-method-of-least-squares-in-multiple-linear-regression/","created":"2024-08-31T23:47:13.914-04:00","updated":"2024-06-06T15:10:19.453-04:00"}
---

202405181945
Status: #idea
Tags: [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]]
# The Method Of Least Squares in Multiple Linear Regression
![Pasted image 20240606151018.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606151018.png)

The logic is identical to the [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] case, except that we now need to represent everything in matrix form.

This changes the formulas since now we need to find our estimators using tensor calculus and stuff, but if you understand the logic in the single-variate case, doing it for multiple variables is just deriving the formulas using matrices all over again.

I will not bother going through the derivation mainly because I got a textbook that does it already, so I will just paste the formulas.

## The Importance of $SS_{res} (\sum_{i=1}^n e^i)$
Pretty much all the formulas below are derived through some representation of the sum of error which we're trying to minimize. It is good to familiarize oneself with the ways to do so.

## Formulas
## $\hat \beta =$
![Pasted image 20240518200034.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518200034.png)

## $SS_{res} = SS_{Error} =\sum_{i=i}^n e_i^2 = \sum_{i=i}^n (\boldsymbol Y_i - \hat Y_i)^2=$ ![Pasted image 20240518195411.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518195411.png) 
From the equation for $\hat \beta$ and $SS_{res}$ we can simplify the equation for $SS_{res}$ to 
![Pasted image 20240518201001.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518201001.png)

The degree of freedoms of $SS_{res}$ in the multiple linear regression case is $n-k$ where $k$ is the number of parameters. This is nothing more than a generalization of the [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] which had $n-2$ degree of freedoms since we needed 2 error terms to be fixed to satisfy the normal equations.

Therefore we can compute the $MS_{res}$ as
![Pasted image 20240518201404.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518201404.png)
The image above tells us that $SS_{res}$ is distributed according to a $\chi^2$ with $n-k$ degrees of freedom.

## $SS_{total} = \sum_{i=1}^n(Y_i - \bar Y)^2 =$
![Pasted image 20240518201936.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518201936.png)
First $SS_{T}$ has $n-1$ degree of freedoms.

In matrix form this is written as:
$$
SS_{T} = Y^TY - n\bar Y^2
$$
Where $\bar Y$ is a scalar quantity.

Since we have a formula for $SS_{res}$ and a formula for $SS_{T}$ through the relation $SS_{T} = SS_{res} + SS_{reg}$ we can derive that:

## $SS_{reg} = \sum_{i=1}^n (\hat Y_i - \bar Y)^2 =$
![Pasted image 20240518202222.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240518202222.png)

$SS_{reg}$ has how many degree of freedoms?

Recall that $DF_{total} = DF_{reg} + DF_{res}$, since we know that $DF_{total}$ is $n-1$ and that $DF_{res}$ is $n-k$ where $k$ is the number of parameters, it follows that $n-1-(n-k)$ or in a civilized world $k-1$ will be the number of degrees of freedom of $SS_{reg}$.

Therefore $MS_{reg}$ is:
$$
MS_{reg} = \frac{SS_{reg}}{k-1}
$$


## References
[[1. Cosmos/The Method Of Least Squares In Simple Linear Regression\|The Method Of Least Squares In Simple Linear Regression]]
[Video on Multiple Linear Regression](https://www.youtube.com/watch?v=LhGFXO1NQLk&list=PLbMVogVj5nJSpj5sl-8tdKARg1lw2wEa-&index=6)
