---
{"dg-publish":true,"permalink":"/2-white-holes/references/understanding-deep-learning/"}
---

202405170013
Status: #reference
Tags: [[Deep Learning\|Deep Learning]]
# Understanding Deep Learning

## Introduction
He gives an overview of everything. Going over supervised, unsupervised and reinforcement learning. He explains how [[Deep Learning\|Deep Learning]] is a really potent way to do machine learning that is state of the art in many areas.

it's always a process of converting input into vectors, passing them into a mathematical formula called a model, taking the logits of that model which are also in a numerical format and then transforming those raw outputs into something that makes sense to the end-user.

The book focuses on a family of models called [[Generative Unsupervised Models\|Generative Unsupervised Models]] obviously this family is a subset of the [[Unsupervised Models\|Unsupervised Models]] which are trained using [[Unsupervised Learning\|Unsupervised Learning]] techniques. 

The idea of [[Generative Unsupervised Models\|Generative Unsupervised Models]] is to get a model to learn the probabilistic distribution of its data so that it becomes able to effectively predict it. Similarly to how the first deep learning NLP models that broke out were trained to predict the next words in a wikipedia article, generative unsupervised models thanks to their deep understanding of the probabilities of the data on which they were trained become able (if the trained on enough data) to generate new data that is probalistically identical to whatever it was trained.  As I was writing I wondered why if that's the case, it is demonstrably true that GPT uses lingo that people wouldn't typically use, and I tried to answer that here : [[1. Cosmos/Why ChatGPT Tweaks So Much\|Why ChatGPT Tweaks So Much]]

It is important to note that as far as we are aware the model does not "understand" the meaning of what it's saying and cannot "think", this can be substantiated by the fact that no matter how easy or hard a question is, the "cost" of a given question is totally deterministic. Currently such models are glorified applications of the [[1. Cosmos/Multinomial Distribution\|Multinomial Distribution]].

They also bring up [[Latent Variables\|Latent Variables]] which are apparently based on the idea that a lot of the time you can greatly reduce the dimensionality of a problem by observing that the [[1. Cosmos/Sample Space\|Sample Space]] of solutions is a subset of the much bigger set of possible things. The set of grammatically-correct sentences is a much smaller set than the set of all string of words in the English language.

Finally the book talks about [[Reinforcement Learning\|Reinforcement Learning]] and the [[temporal Credit Assignment Problem\|temporal Credit Assignment Problem]]. The former is something that is used in many contexts, not the least of which being [[Genetic Algorithms\|Genetic Algorithms]] where the goal is to train agents to accomplish given objectives when the optimal way to achieve that objective is not necessarily known. The goal is that we want to reward the model for reaching checkpoints or accomplishing our objectives and progressively get the model to improve. There are a few considerations in such problems, first there's the dichotomy between exploration and exploitation. WHen the model has been trained even a  tiny bit, it might reach a point where it is able to gain rewards, no amtter how modest they are, in such contexts who is to say if it should try to exploit what it knows and maximize that, ot ig it should instead explore the [[1. Cosmos/Sample Space\|Sample Space]] and try to find novel solutions. In a sense it's up to you, but who's to say you are right? The second issue is that a lot of the time there will be time that elapses between the agent doing a beneficial action and it earning a reward. At which point while it will be incentivized to repeat its actions, which actions exactly lead to success is obfuscated. It's kinda like how confused you are when your parents are mad about you for something that happened a hours or sometimes days ago but that they hadn't brought up; now you gotta sit there and think... "Uh... when did I fuck up?"

The book touches on the supra important subject of AI ethics. How to ensure that AI does not fuck us all over. It does not really give answers, but it shows how many problems AI could raise along with how powerful it can be and directs towards courses to learn about it. 
https://ethics-of-ai.mooc.fi/





## Supervised Learning
This is really the fundamentals of machine learning. This is the most straightforward way to get the fundamentals of machine learning and deep learning, and Simon does an amazing job of keeping it short while covering what has to be covered. I wish some more emphasis had been put on [[Generative Models\|Generative Models]] since it was the first time I heard of the term (as opposed to [[Discriminative Models\|Discriminative Models]].) But to be fair, considering it was the first time and likely the last, it is likely not too big of a loss.
[[1. Cosmos/Supervised Learning\|Supervised Learning]]

## References
[[1. Cosmos/Understanding Deep Learning ~ Flashcards\|Understanding Deep Learning ~ Flashcards]]
