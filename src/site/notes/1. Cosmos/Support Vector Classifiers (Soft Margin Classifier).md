---
{"dg-publish":true,"permalink":"/1-cosmos/support-vector-classifiers-soft-margin-classifier/","created":"2025-01-22T11:17:14.248-05:00","updated":"2024-12-11T22:59:04.661-05:00"}
---

202412112230
Status: #idea
Tags: [[1. Cosmos/Linear Methods for Classification\|Linear Methods for Classification]]
State: #nascient
# Support Vector Classifiers (Soft Margin Classifier)
These classifiers build upon [[1. Cosmos/Maximal Margin Classifier (Optimal Separating Hyperplaene)\|maximal margin classifiers]] and tackle the cases where the assumption of linear separability is not tenable.

After all, there are more cases than not where it isn't true, moreover even when it is true, using the maximal margin makes us overly sensitive on a few points and might force our hand to choose variance that is quite close to the observations.

The support vector classifier essentially says, "Just chill, we can afford to lose that much" and maximizes while allotting from the start a budget of classifications.

It allows observations to not only be on the wrong side of the [[Margin\|margin]], but also on the wrong side of the [[1. Cosmos/Hyperplane\|hyperplane]] as well, the latter is inevitable if the data is not linearly separable.

![Pasted image 20241211223701.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020241211223701.png)

We see that it is really similar to the function we try to optimize for [[1. Cosmos/Maximal Margin Classifier (Optimal Separating Hyperplaene)\|maximum margin classifiers]] except that we now have an allowance on the right hand side that allows for classification errors, as long as the total of those errors is contained within the budget $C$.

Let's note a few things about the formula:
- The error term $\epsilon_i$ represents the error associated with the $i$th observation
- If the error term $\epsilon_i=0$, it means $x_i$ is on the right side of the margin
- If the error term is $\epsilon_i \in (0,1)$ we see that $x_i$ has violated the margin, it is still on the right side but penetrated the margin.
- If the error term is greater than $1$, then $x_1$ has not only penetrated the margin, it is fully on the wrong side.
If $C=0$ then this model is the same as the [[1. Cosmos/Maximal Margin Classifier (Optimal Separating Hyperplaene)\|Maximal Margin Classifier (Optimal Separating Hyperplaene)]].

By the facts we just explained, enforcing $C=k$ ensures that no more than $k$ values can be on the wrong side, so we are capping our error rate (on the training set) from the start which is quite powerful.

As $C$ increases, the margin increases as we are more tolerant, the opposite happens as $C$ decreases. 

For big $C$, the bias increase as the model is more tolerant and fit less well to the model, but the variance should hopefully decrease as we are not as stringent on fit to the specific dataset. For smaller $C$ we'd expect the opposite to happen with the extreme case being the [[Linearly Separable\|Linearly Separable]] case.

Like all other tuning parameters before it, $C$ is often chosen through [[Cross Validation\|Cross Validation]].

For this method, the [[Support Vectors\|Support Vectors]] are extended to include not only the points that touch the margin, but also all the points that are on it, as logically moving those points would eat more or less within our margin.

All the observations that are neatly labeled do not affect fit.

This makes this model much more robust than other similar methods. [[1. Cosmos/Linear Discriminant Analysis (LDA)\|Linear Discriminant Analysis (LDA)]] for one, depends on the mean of all the variables within one class to predict things. [[1. Cosmos/Naive Bayes\|Naive Bayes]] similarly computes the prior and likelihood based on observations, so changing those observations might significantly affect our fit. 

This is in stark contrast to [[1. Cosmos/Logistic Regression\|Logistic Regression]] which is not affected by observations beyond the decision boundary.

But what if we need something... non-linear? Cue in the [[1. Cosmos/Support Vector Machine (SVM)\|Support Vector Machine (SVM)]] which is the final generalization we consider.

## References
