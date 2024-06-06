---
{"dg-publish":true,"permalink":"/1-cosmos/chi-squared-distribution/"}
---

202405310819
Status: #idea
Tags: [[Probability Distributions\|Probability Distributions]]
State: #nascient
# Chi-Squared Distribution
![Pasted image 20240531081951.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240531081951.png)

## Properties

## Adding independent $\chi^2-$distributed random variables
Let $X$ be distributed according to $\chi^2(r_x)$ and $Y$ according to $\chi^2(R_Y)$ and let them both be independent such that:
$$
f(x,y)=f_X(x)f_y(y), \forall x,y 
$$
Then:
$$
X+Y \sim \chi^2(r_X+r_Y)
$$
*Prove this using the Moment Generating Functions of $\chi^2$.*

## Dividing independent $\chi^2-$distributed random variables
$$
\frac{X}{Y} \sim F_{r_X, r_Y}
$$
Where $F$ is a [[Fisher Distribution\|Fisher Distribution]].

## Squaring a [[1. Cosmos/Normal Distribution\|$N-$distributed]] random variable ($N(0,1)$)
When you square a normally distributed random variable with mean $0$ and $\sigma^2$ 1, it becomes a
$$
Z^2\sim\chi^2(1)
$$

## Squaring [[1. Cosmos/Normal Distribution\|$N-$distributed]] independent random variables
From what we now from a [[1. Cosmos/Normal Distribution\|Normal Distribution]], you can always standardize it (make it $N(0,1)$), by substracting the mean and dividing by the standard deviation.

And by [[1. Cosmos/Chi-Squared Distribution#Squaring a Normal Distribution $N-$distributed random variable ($N(0,1)$)\|#Squaring a Normal Distribution $N-$distributed random variable ($N(0,1)$)]] we know that such a random variable squared will have $\chi^2$ distribution with $1$ degree of freedom.

Finally, by [[1. Cosmos/Chi-Squared Distribution#Adding independent $ chi 2-$distributed random variables\|#Adding independent $ chi 2-$distributed random variables]] we know that the result will be a $\chi^2$ with $r_X+r_Y$ degrees of freedom. Take it all together and you obtain:

For $n$ independent **normally** distributed random variables, then:
$$
\sum_{i=1}^n(\frac{X_i-\mu_i}{\sigma_i})^2 \sim \chi^2(n)
$$
## References
