---
{"dg-publish":true,"permalink":"/1-cosmos/fragment-shader/","created":"2025-01-22T11:17:14.071-05:00","updated":"2024-07-20T03:52:27.413-04:00"}
---

202407200352
Status: #idea
Tags: [[Computer Graphics\|Computer Graphics]]
State: #nascient
# Fragment Shader

![[Pasted image 20230729172828.png\|Pasted image 20230729172828.png]]
This is where we set the color of each fragment.
There is a lot more complexity behind the hood, but yeah, that's basically what this does.

## Why fragment instead of pixel?
Because we're not sure, yet if there's going to be a 1-1 mapping of the fragments it's working on, to the pixels on your screen. Everything will be treated, and in cases where the programmer is working with a 1080p resolution, it will probably map; but this is not guaranteed. So it's called a fragment instead of a pixel, because it's a fragment of the full picture.


## References
