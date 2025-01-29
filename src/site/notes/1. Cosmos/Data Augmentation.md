---
{"dg-publish":true,"permalink":"/1-cosmos/data-augmentation/","created":"2025-01-22T11:17:13.935-05:00","updated":"2024-05-23T01:15:27.380-04:00"}
---

202404291727
Status: #idea
Tags: [[Deep Learning\|Deep Learning]]
# Data Augmentation

### Reduce the need for Labelling
It is a way to reduce the need for manual labelling by effectively 10x (or any sensible multiple) the image. It consists of distorting an image in a way that does not fundamentally change the underlying thing it represents (for example flipping, rotating, cropping) such that on each epoch the model is trained on a modified version of the same image.

Therefore, we only need to label each image once. This is not the main use for data augmentation, but it is an interesting characteristic to point out.


## References
[[2. White Holes/References/Practical Deep Learning for Coders\|Practical Deep Learning for Coders]]