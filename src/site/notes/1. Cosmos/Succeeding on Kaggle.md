---
{"dg-publish":true,"permalink":"/1-cosmos/succeeding-on-kaggle/"}
---

202407200328
Status: #idea
Tags: [[Kaggle\|Kaggle]]
State: #nascient
# Succeeding on Kaggle

The main rule is to iterate as much as possible. You should submit everyday until either you are satisfied with the result, or the time allocated as run out. 

DO NOT MAKE THE ERROR OF SPENDING MONTHS ON **ONE** SUBMISSION.

Good goal : Top 25% (it's a good sign of understanding )
1. Find a starting model (research and make sure you understand), setup the environment, train your first model, submit. Boom you now have a baseline.
2. Change your model to something better and see what seemed like a weak point in your first model.
3. Iterate, being super aware of the context clues and errors you might have had.
4. Iterate. Iterate. Iterate!

Good things to keep in mind..
- Test Time Augmentation, a nifty trick at prediction time (after training the model) where we pass multiple augmentations of the same image and do an averaging of inferences of this subset of the same image. Usually leads to better results.
- You are not forced to use squares, if all images are of the same aspect ratio, you can resize all the images to rectangles. As long as all the images are the same size you are good.
- Do not be afraid of failure, try stuff and iterate.
- Have something else open for you to work on as you work for the model to train, there's going to be a lot of waiting.
- **Do research!** Resnet is not the best architecture anymore for a lot of things (besides maybe speed) and sometimes you can get crazy improvements at no extra time cost just by using a more appropriate architecture. Being aware of the trends pays.

A lot of this applies no matter what type of competition yo do. As long as you iterate a lot.

#machinelearning #kaggle

## References
