---
{"dg-publish":true,"permalink":"/1-cosmos/neural-networks/","created":"2024-08-31T23:47:13.536-04:00","updated":"2024-05-22T02:05:39.979-04:00"}
---

202405220058
Status: #idea
Tags: [[Machine Learning\|Machine Learning]] 
# Neural Networks
Fundamentally all a neural network is, is an infinitely flexible class of function, that can be anything and everything you want; from the straightest of line, to the squiggliest of squigglies. As Josh Stalmer (from StatQuest) calls it, it's not much more than Big Fancy Squiggly Fitting Machine. 

Neural Networks are made of a few components which are all better treated in their own notes, because I foresee that anything more than surface level will evolve into something... complex.
## The 4 Pillars of Neural Networks
The fundamental components:
- Nodes ([[Neurons (Machine Learning)\|Neurons (Machine Learning)]]) : The "neural" in neural networks. They are not much more than small functions, in a network (yes I said it) of functions. They take in a set of inputs from the previous layers (or alternatively from the ether if we are the input layer) and then combine all the inputs along with respective weights and outputs them either to the next layer of neurons, or back into the world. Note that two neurons on the same [[Layer\|Layer]] never talk to each other.
- [[Layers (Machine Learning)\|Layers (Machine Learning)]]: This is the name given to groups of related but mutually independent [[neurons (Machine Learning)\|neurons]]. While technically it is possible to approximate any function by doing everything on one layer. something called [[Shallow Neural Networks\|Shallow Neural Networks]]. In practice, unless we are in an educational context we will use anything from a few layers to ... arbitrary big finite numbers! Why? [[Shallow Neural Networks\|Shallow Neural Networks]] become too big and cumbersome for anything beyond simple demonstrations and pedagogic material. Adding a neurone is to adding a layer what addition is to multiplication; if it wasn't for the ability to add arbitrarily many layers to a neural networks, [[Machine Learning\|Machine Learning]] and [[Deep Learning\|Deep Learning]] would have died in the 20th century and remaining the object of phantasms and fiction without much practical use (*cue in [[Alchemy\|Alchemy]]*)... I really gotta watch [[Fullmetal Alchemist\|Fullmetal Alchemist]]...
- [[1. Cosmos/Weights (Parameters)\|Weights (Parameters)]]: In the current paradigm of machine learning, this is what actually changes when you say "I am training a model", or "my model is learning." The ideas are really identical to what is explored in [[1. Cosmos/Simple Linear Regression\|Simple Linear Regression]]. I have some function(curve) that I am trying to fit, I need to find (estimate) the best parameters such that model fits the data that I have observed and pray that it generalizes. Well in general you are a little more active than in prayer and have more bargaining power ([[Learning Rate\|Learning Rate]], [[Activation Functions\|Activation Functions]], [[Dropout\|Dropout]], [[Optimizers\|Optimizers]], etc.), but yeah that's the gist. The main difference is that instead of doing fancy calculus and other derivations , you use the good ol [[1. Cosmos/Chain Rule\|Chain Rule]] (yes the one from [[Calculus\|Calculus]]) to compute how to improve the parameters (How to reduce the [[1. Cosmos/Loss\|Loss]]) and and let the [[Machine Learning\|Machine Learning]] magic ([[Backpropagation\|Backpropagation]]) occur. This will be treated more rigorously in the actual note for [[1. Cosmos/Weights (Parameters)\|Weights (Parameters)]] and [[Backpropagation\|Backpropagation]].
- [[Activation Functions\|Activation Functions]]: One of the tools you have to bargain with the machine, they give you the ability to give some sort of meaning to a given output (whether it be from a [[neurons (Machine Learning)\|neurone]] or a specific [[Layers (Machine Learning)\|layer]]). For example, if the outputs of my [[Output Layer\|output layer]] are supposed to be probabilities, but that in their current form they do not sum to $1$, have potentially negative values, etc. I could leave them as is (if I am a masochist), or I could pass them through a [[Softmax\|Softmax]] and not have to worry about any of that. [[Activation Functions\|Activation Functions]] can be any function that you want as long as it makes sense in your case, but common ones are the [[Logistic Function\|Logistic Function]], the [[Rectified Linear Units (RELUs)\|Rectified Linear Units (RELUs)]] (the GOAT), and the [[Softmax\|Softmax]].

These are the components of neural networks, and I hope you know understand why I decided to keep everything to their own notes. 

## Why Neural Networks?
Fundamentally, because they are a universal approximators and are comparably straightforward when it comes to training them. 

First, the first point. Yes, this sounds as cool as it sounds.
It means that it is provable mathematically that a neural network given enough layers and neurons can approximate any... **ANY** mathematical function you could think of. See [[Universal Approximation Theorem\|Universal Approximation Theorem]].

The thing is more than a few classes of functions can do that, like the [[Polynomials\|polynomials]] we all know and love can do that as well. So then why neural networks?

Fundamentally because they are dead simple and can be used like in pretty much any context. The list of their benefits would be too big but a few are:
- Can be trained on much higher dimensionality data than other methods (see [[Convolutional Neural Networks (CNN)\|Convolutional Neural Networks (CNN)]])
- Non-linearity allow the modelling of complex functions with comparatively less parameters
- Features are allowed to "emerge" from the data rather than being explicitly baked in (see [[Collaborative Filtering\|Collaborative Filtering]])
- Pretrained models and Transfer Learning, as opposed to other types of methods, neural networks excel in its ability to be repurposed and reused by simply [[Finetuning (Machine Learning)\|finetuning]] it to our data. Allows us to stand on the shoulders of giants, and train record-breaking and even field-revolutionizing models with even with small datasets.

No other method boast the same level of flexibility, generalizability, effectiveness and power. There is a very real issue with the fact that as things stand a lot of [[Machine Learning\|Machine Learning]] models, especially on the [[Deep Learning\|Deep Learning]] side of things are inscrutable black boxes. Still their other advantages make that significant downside palatable. This is the difference between [[1. Cosmos/Inference\|Inference]] and [[Prediction\|Prediction]]. If what we care about is how specific elements relate to each other, neural networks are terrible; but for anything else they are a game-changer and are guaranteed to work.

*Caution, do not let your hype over [[Artifical Intelligence\|Artifical Intelligence]] and neural networks take you over. While machine learning and neural networks are extremely powerful and high quality mithril hammers, not all the problems in your life require hammering nails into a drago... Pause, I swear as I wrote that I wasn't thinking of anything...*

(I am thinking of an innuendo game, I am not **that** weird.)

*Simple and interpretable models like [[1. Cosmos/Decision Trees\|Decision Trees]], and [[1. Cosmos/Random Forests\|Random Forests]] are still relevant and can often offer similar if not better results on the same data as the neural network alternative. Sometimes the data at hand simply does not have enough "hidden features" to make the overhead of a neural network worth it. Furthermore, even if we are adamant about using a neural network, first creating models using simpler methods like [[1. Cosmos/Linear Regression\|Linear Regression]], [[Tree-Based Methods\|Tree-Based Methods]] and whatnot as value even simply as a baseline. You do not want to spend weeks optimizing a model, trying different learning rates, and learning schedules, tweaking the number of epochs and the whole shebang just to realize your model does about the same (or potentially worse) than a [[1. Cosmos/Multiple Linear Regression\|Multiple Linear Regression]] model you fitted in 5 seconds in R.*
## References
