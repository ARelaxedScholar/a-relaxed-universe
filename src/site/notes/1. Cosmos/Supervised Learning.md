---
{"dg-publish":true,"permalink":"/1-cosmos/supervised-learning/"}
---

202405170137
Status: #idea
Tags: [[Machine Learning\|Machine Learning]]
# Supervised Learning

Fundamentally the idea of supervised learning is simply to fit a curve to data.

That is literally it.
Everything else is just mathematical jargon and calculus (to find the right parameters and what not.) I lied, there's also some [[Probability\|Probability]] and [[Statistics\|Statistics]] in there as well as [[Linear Algebra\|Linear Algebra]]...

The rest is just math to derive your parameters.

Supervised learning can be summarized as the following equations:
$$
y=f[\boldsymbol x, \phi]
$$
$$
L=\text{some function that quantifies how much the model fucked up}
$$

$y$ here is a vector of observations, $f$ is whatever class of mathematical functions we think is a appropriate to fit in our model. In the case of [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]] and [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]] they are linear functions, but in the case of [[Deep Learning\|Deep Learning]] it will invariably be some kind of [[1. Cosmos/Neural Networks\|neural network architecture]]. Finally we have $\phi$ which represents all our parameters.

When someone says with the chest puffed that they are "training" a model or that the model "learned" from the data, it is nothing more than fancy speak for "we mathe-magically tweaked the vector of parameters $\phi$ until it gave us results that made sense."

The above sentence might change in the future with the advent of things like [[KANN\|KANN]] which allow us to train the activation functions as well, but that is besides the point for now.

## Methodology
Well, it depends, and if you are hardy enough for some of the more well-known models you could actually sit down to derive the best parameters (those that minimize the loss) by hand.

But in [[Deep Learning\|Deep Learning]] the models we are dealing with are way too big for that, and even if they weren't we have computers to do the job. So the idea is more or less always something along the line of:
1. Initialize the parameters at random values (Making sure those values are in the right ballpark can make the difference between a model that is impossible to train, and one that trains in seconds)
2. Compute the loss function $L$ for those randomly initialized parameters (ie: [[Least Square Error\|Least Square Error]])
3. Compute the [[Gradient\|gradient]] for that loss function (it represents the direction of steepest ascent) 
4. Back-propagate it to your parameters (now they all should have data that shows how to **increase** the loss)
5. Take a step proportional to your [[Learning Rate\|Learning Rate]] in the direction **opposite** to the gradient.
6. Repeat until either:
   - Gradient is $0$ and no more improvement can be made
   - We've completed to train for all the allocated [[Epochs\|epochs]]
   - We have run out of time
   - We have run out of resources
   - The model's loss has been stagnating for a given number of epochs
   - The model's loss has actually started going up
   - etc.

This is all there is to it fundamentally, we just want to find the parameters often called weights, which minimize our loss function or in math-speak:
$$
\hat \phi = argmin[L[\phi]]
$$

Since we never know the actual [[Population Statistic\|population statistics]] so-to speak of our model, we need to approximate them. And the above equation just means "the vector of parameters that best estimate $\phi$ is given by the set of parameters that minimize the loss function." 

The rest is just the math to derive the parameters, and whatnot.

Finding architectures is a rough task as well.

## Generative vs Discriminative Models
[[Discriminative Models\|Discriminative Models]]--what we presented above--are models which go the intuitive way of using the regressors or independent variables to predict the dependent variables. [[Generative Models\|Generative Models]] on the other hand, choose the unorthodox approach of "generating" the measurements/regressors that could have lead to the observation from the observations; essentially inverting the direction.

So while discriminative models take the form $$
\boldsymbol y = f[\boldsymbol x, \phi]
$$
generative models take the form:
$$
\boldsymbol x = g[\boldsymbol y,\phi]
$$
Uh...
What?

Yeah, we are finding an equation for $x$ using $y$, you are not reading wrong. This has the obvious disadvantage that this model cannot actually be used "as is" to make any inference since we are currently finding $x$.

As a result, we need to invert this model to get:
$$
y = g^{-1}[\boldsymbol x, \phi]
$$
Now, this looks like it should. Such a model has an advantage, notice how we started by generating our model from $\boldsymbol y$? This is meaningful in contexts where the value of $\boldsymbol y$ is actually meaningful as it comes to what kind of data might have generated; if we have domain knowledge that lead us to believe that these or that things can be garnered from the outputs, such a model allows us to bake that knowledge into the model. This is quite a significant benefit.

So why have you never heard of the term? Because the above equation assumes that $g$ is invertible. Note that even when it is invertible, it does in no way mean that the derivation will be trivial. It can be a huge pain to compute so huge in fact that despite it's big advantage, it's standard [[Discriminative Models\|discriminative counterpart]] is by far the most used.

After all, while discriminative model lack that "bake-in knowledge" ability, they more than make up for it by their flexibility and simplicity. We can already by [[Universal Approximation Theorem\|Universal Approximation Theorem]] approximate any function we could ever want to use with a few [[Rectified Linear Units (RELUs)\|Rectified Linear Units (RELUs)]] anyways.
## References
[[2. White Holes/References/Understanding Deep Learning\|Understanding deep Learning]]