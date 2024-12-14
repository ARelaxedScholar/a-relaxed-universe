---
{"dg-publish":true,"permalink":"/1-cosmos/linear-methods-for-classification/","created":"2024-12-09T09:17:58.659-05:00","updated":"2024-12-13T08:53:59.481-05:00"}
---

202412090918
Status: #idea
Tags: [[1. Cosmos/Classification\|Classification]]
State: #nascient
# Linear Methods for Classification

There are two standard ways and a third that kinda work but is theoretically hard to justify basically all the time. There are more ways that end up having a linear boundary when developped, but ISLR talks about these two. :shrug:

We focus here on [[1. Cosmos/Logistic Regression\|Logistic Regression]] and [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]].

The idea of Linear Methods for classification is simply that our data exists on some topological space and we make the assumption that lines exist that can separate the labels of our data neatly.
This is a simple but extremely powerful idea because if you remember anything from linear regression, by *linear*  we mean linear in the coefficients.

Hence, we are perfectly in our rights to allow $X, X^2, X^2, log(X)-1$ to be features that we consider and to try to find linear decision boundaries in whatever disgusting space this outputs. We know that in the original space based on $X$, these lines will be topsy-curvy and sexy...

Scratch that last line...

Still, we can get complexity and curves out of linear models by augmenting them with themselves. In practice, we call linear any method for which a transformation exists that make the equation linear which is why even though:
$$
P(G=1|X=x)=\frac{exp(\beta_0+\beta^Tx)}{1+exp(\beta_0+\beta^Tx)}
$$
$$
P(G=2|X=x)=\frac{1}{1+exp(\beta_0+\beta^Tx)}
$$
where $G$ is a binary class, we can easily compute the log-odds (logit function) as follows:
$$
log\frac{P(G=1|X=x)}{P(G=2|X=x)}=\beta_0+\beta^Tx
$$
which is indeed linear, and so [[1. Cosmos/Logistic Regression\|Logistic Regression]] is in that class of [[Classifiers\|Classifiers]] (well technically it's a regressor, like it's in the name, but it regresses a probability that we then use for classification, so kinda potay-to, potah-toe?)

## Why not Linear Regression?
In practice, sometimes you could. If you have exactly two classes, it is quite possible that your linear regression model will give you similar performance to a more standard linear classification model.

So why not?
- The assumptions are often not justifiable (we require normality of $Y$ remember)
- The predictions of the model can and often are negative/above one which is nonsensical if they represent posterior probabilities. Even if within the training scope this doesn't happen in theory we could always get something where the regressed value is beyond the range of probabilities.
- For anything more than 2 classes, there will likely be a masking problem where since we can only fit **one** line, some class will be ignored (masked) even in cases where data is clearly linearly separable. (we could probably just fit two lines then? but the other problems still exist)
	![shot-2024-12-09_09-35-17.jpg](/img/user/3.%20Black%20Holes/Files/shot-2024-12-09_09-35-17.jpg)
from  Elements of Statistical Learning page 124

So yeah, that's why.

So what do we do if we want a linear decision boundary? There's three main candidates, but ISLR mentions two at this point, let's list them all:
- [[1. Cosmos/Logistic Regression\|Logistic Regression]]
- [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]]
- [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]]
## References
[[A Comparison of Linear Discriminant Analysis, Quadratic Discriminant Analysis, Logistic Regression and Naive Bayes\|A Comparison of Linear Discriminant Analysis, Quadratic Discriminant Analysis, Logistic Regression and Naive Bayes]]