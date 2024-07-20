---
{"dg-publish":true,"permalink":"/2-white-holes/references/mat-3375-regression-analysis/"}
---

202405271901
Status: #reference
Tags: [[1. Cosmos/Regression\|Regression]]
# MAT3375(X) ~ Regression Analysis

> [!NOTE] Excerpt from [Catalogue MAT3375](https://catalogue.uottawa.ca/search/?P=MAT%203375)
> Modeling relationships between outcome (dependent) variables and covariates (independent variables) using simple and multiple linear regression models. Estimation and hypothesis testing using least squares and likelihood methods. Performing model diagnostics and assessing goodness of fit properties. Variable selection and finding the best fit. Non-linear regression and transformations. Weighted regression and generalized least square. Analysis of data using statistical software packages.


## [Lecture 1](https://uottawa-ca.zoom.us/rec/play/hhWqWTFbGumaC9CGMB7FI1pRBJz7_caTPIDQqNC0bI32JraR83WojoJnyqMNJo9TB0mVNYNI3H5UMiU5.Ocbq2o0cOkQ0vLOz)
![Pasted image 20240606121946.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606121946.png)
The first lesson starts slowly with the basics, we are introduced with the most fundamental regression technique [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]], and we set the tempo. We will not be dawdling, by the end of the lesson we have seen how to derive the formula for the estimators in the simple case, how to derive the formula for the different inference techniques, and the distribution of the different parameters involved.

The course will be fast-paced.

### Lesson Points:
[[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]
[[1. Cosmos/The Method Of Least Squares In Simple Linear Regression\|The Method Of Least Squares In Simple Linear Regression]]
[[1. Cosmos/Properties of Least Square Estimators in SLR\|Properties of Least Square Estimators in SLR]]

## [Lecture 2](https://uottawa-ca.zoom.us/rec/play/BpogQG2AOzwPLN-MibC4_82T5rg8RhXiJEpw8t0ojYN6lbk7etIF9c6gAe08nnHqtbH3dOhov5BFu3YR.K2-52cxdDcyPf_BD)
![Pasted image 20240606125243.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606125243.png)
We start by reviewing simple linear regression.

We then take the rest of the period to explore [[1. Cosmos/Analysis of Variance (ANOVA)\|Analysis of Variance (ANOVA)]] after briefly introducing multiple linear regression.

### Lesson Points
[[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]]
[[1. Cosmos/Analysis of Variance (ANOVA)\|Analysis of Variance (ANOVA)]]
[[1. Cosmos/Hypothesis Testing about Rho\|Hypothesis Testing about Rho]]


## [Lecture 3](https://uottawa-ca.zoom.us/rec/play/u95zJzJFDv3avtN155Yj7umcc8wglINICRqJm13qizyCjD2_dnHhhtc_Rio_GQJMeXQCjuZPCsmY6eq8.Aox29xcFdY3FcSSo )
We directly start with [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]].
Which can be seen as a generalization of [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]].

Since it would quickly become unwieldy to do the same kind of algebra we did for simple linear algebra, on arbitrarily many parameters, it is a pressing issue to find a way to do calculations once so that they will apply to any number of parameters.

And what better way to do that than to resort to [[Linear Algebra\|Linear Algebra]] and matrices? Indeed, [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]] makes full use of matrices and matrix calculus to derive it's formulas. In this lesson we cover that, and 
go over the formulas to remember for each part.

### Lesson Points:
[[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]]

## [Lecture 4 ~ Start of Model Adequacy Checking](https://uottawa-ca.zoom.us/rec/play/YewFjwydDP3HfFcsEBDk3q8jZ6xgyi8YJOmG8o2Ij8G-hoERI_A4OKYfPZEUfvtXaVWyVqcC2BqcK5kO.zPSO7-WKu3rgMGFC)
![Pasted image 20240606154755.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240606154755.png)
We start seeing generalization of [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]].

More specifically, how do we deal with [[Categorical Data\|Categorical Data]].

### Lesson Points
[[1. Cosmos/Multiple Linear Regression#Special Cases\|Multiple Linear Regression#Special Cases]]
[[1. Cosmos/Multiple Linear Regression#Hypothesis Testing\|Multiple Linear Regression#Hypothesis Testing]]

## [Lecture 5 ~ A Masterclass on Confidence Intervals](https://uottawa-ca.zoom.us/rec/play/sKz8BqUkYFr7fhoJun-CVCqTqPwazd6gph_Br8KjCBgRORY_ai2tNJzPukm1P0hXo7mgaWbv_L6E85hF.8nHzezAtBWWR3hMp) 
As expected, here we focus on how to compute confidence intervals:
We also touch on the extra sum of squares method, which can be seen as the big brother of the [[1. Cosmos/Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)\|Test On Individual Regression Coefficient (Assuming We know our Model Is Significant)]].
### Lesson Points
[[1. Cosmos/Multiple Linear Regression#Confidence Intervals\|Multiple Linear Regression#Confidence Intervals]]
[[1. Cosmos/Extra Sum of Squares Method\|Extra Sum of Squares Method]]



## [Lecture 6 ~ Model Adequacy](https://uottawa-ca.zoom.us/rec/play/4naxqP_MMmY6-5KSMWgMbE4m2vE4VSPvoXUSPlK6LOgmqYAp4wNqpqkPXE7o_4zmdPHGcw5qSd522GJt.lecZQCHXav5SIEBQ)
![Pasted image 20240607125532.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240607125532.png)

After spending so much time on building linear models and building intervals for them, we want to be able to check if our model even does a good job. More specifically, does it do a good job purely by chance, or does the assumptions implied by the use of that model respected?

### Lesson Points
[[1. Cosmos/Model Adequacy Checking\|Model Adequacy Checking]]


## [Lecture 7](https://uottawa-ca.zoom.us/rec/play/ikVtCJBpGNiWmiTXq_JC8Kg7RcpoWkW_sQrUWlVlkyiTTZ4m3TUH5X5MWUr-VFtW9K5LcssOzyqqtPBu.sVIXsuOoueDceZnK)
![Pasted image 20240607144239.png](/img/user/3.%20Black%20Holes/Files/Pasted%20image%2020240607144239.png)
So last lecture we checked how to check if the model assumptions held.

This lecture we learn how to correct a model if it seems that assumptions are not correct.

Depending of what assumptions were broken, we will need to use different methods. The methods will pretty much always involve transforming either the response variable, or the predictor variables.
### Lesson Points
[[1. Cosmos/Transformations\|Transformations]]
[[Box-Cox Transformation for Non-Normality\|Box-Cox Transformation for Non-Normality]]

## Lecture 8 ~ Weighted Least Squares
This lecture is fully about weighted least squares, a method that is used when we the variance is not constant. In other words, we use it when the homoscedastitcity assumption is broken.

### Lesson Points
[[1. Cosmos/Weighted Least Squares (Generalized Least Squares)\|Weighted Least Squares (Generalized Least Squares)]]
## References
[[1. Cosmos/MAT3375 ~ Flashcards\|MAT3375 ~ Flashcards]]
