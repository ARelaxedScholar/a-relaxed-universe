---
{"dg-publish":true,"permalink":"/1-cosmos/chapter-2-deploying-a-model-lesson-2/"}
---


## Chapter 2 ~ Deploying A Model (Lesson 2)
Outlines a few steps:
1. Get Data
2. Clean Data
3. Train Model
4. Be stupid!!
What? Indeed, while this is the traditional way to do it, it is often better and more efficient to train the model with the uncleaned data, and then use the model to clean the data. So...  the actual procedure should be:
1. Get Data
2. Train Model
3. Use Model to Clean Data
4. Retrain Model on that Data
5. Enjoy!

[[1. Cosmos/Data Augmentation\|Data Augmentation]] is the art of turning 1 into 10. The actual definition is any transforms that you apply to an image to effectively multiply our dataset by a factor. Each epoch the same data (images in this context) are being slightly warped and modified to allow the model to better generalise to unseen data. If you are not planning to run multiple epochs it might not be necessary, but if you do want to run more epochs it is not a terrible idea to do so.

A rarely considered approach is to think deeply about the effects of the technology not in the case of what if everything went poorly (as I like to do to prepare), but rather what would be the consequences if everything went as expected. This can have the same effects depending of your psyche, but this is an interesting perspective nonetheless.


[[Backtest:  A Surprisingly Common Term\|Backtest:  A Surprisingly Common Term]]