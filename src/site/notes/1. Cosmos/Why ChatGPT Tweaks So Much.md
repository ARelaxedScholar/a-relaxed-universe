---
{"dg-publish":true,"permalink":"/1-cosmos/why-chat-gpt-tweaks-so-much/"}
---

 dg-publish: true
202405200148
Status: #idea
Tags: [[Mini-Essay\|Mini-Essay]], [[Deep Learning\|Deep Learning]]
# Why ChatGPT Tweaks So Much, Maybe? Idk
*This is pure speculation, and I did not have time to verify it yet. Will get to it when I get to it. I also wrote most of that at 2am hence the incoherence of certain sentences, when I edit this, I'll label it for posterity.*

It raises the question of why ChatGPT uses so many big words that are not commonly used in real life. 

What raises the question? This is a reaction to the line from [[2. White Holes/References/Understanding Deep Learning\|Understanding Deep Learning]]'s first chapter, where Dr. Simon goes over how generative models--in my own words--are nothing more and nothing less than glorified probability distribution samplers. 

A possible answer to this perplexing issue is something called [[Alignment\|Alignment]] this is my own spin on things which is not covered in this part of the [[2. White Holes/References/Understanding Deep Learning\|book]]. But I suppose that such models are first trained in an [[Unsupervised Learning\|unsupervised]] fashion because no one has the time to actually label the entirety of a language for an AI, and even if someone had the time how the hell would they do it. but a model with enough data can get such a deep understanding of the probabilities of a language that it becomes effectively able to speak. Whether or not it understands what it's saying is debatable, but without human input it becomes able to do that. 

But to make sure the model does what we want it to do, and that the model is a correct tool it is further fine-tuned this time on supervised data. questions with answers and whatnot. In so doing, it becomes exceedingly good at answering questions. The issue? The annotators are likely incentivized to write in a professional almost pompous manner that the model now emulates. Result while it writes well, it writes in a way that feels stilted because of how it was aligned. You can "align" it on your own stuff by passing it data to make use of and whatnot but that's that.

## References
[[2. White Holes/References/Understanding Deep Learning\|Understanding Deep Learning]]