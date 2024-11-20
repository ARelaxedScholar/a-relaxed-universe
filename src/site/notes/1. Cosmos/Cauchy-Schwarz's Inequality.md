---
{"dg-publish":true,"permalink":"/1-cosmos/cauchy-schwarz-s-inequality/","created":"2024-08-31T23:47:13.558-04:00","updated":"2024-05-30T23:11:12.077-04:00"}
---

202405302242
Status: #idea
Tags: [[Important Inequalities\|Important Inequalities]]
State: #nascient
# Cauchy-Schwarz's Inequality
It states that given two vectors $\vec u, \vec v$ their dot product will always be lesser or equal to the product of the magnitudes, so:
$$
\vec u\cdot \vec v \leq ||\vec u|| \times ||\vec v||
$$

In probability it becomes:
$$
E[XY]^2 \le E[X^2]E[Y^2]
$$
This inequality is cool because it allows us to put a bound on the covariance of two [[1. Cosmos/Random Variable\|random variables]]. Indeed just replace the $X$ and $Y$ by $X-\mu_X$ and $Y-\mu_Y$ and from this inequality you can show that there's a bound on the covariance. 

Not only that, by doing nothing more than simple manipulation of the above expression you obtain that $\rho^2$ is less or equal to $1$.

You can prove it using the [[Proof for Cauchy-Schwarz's Inequality using Semi-Positive Definite Matrix\|Proof for Cauchy-Schwarz's Inequality using Semi-Positive Definite Matrix]]
You can also prove it directly without resorting to [[Linear Algebra\|Linear Algebra]].
## References
