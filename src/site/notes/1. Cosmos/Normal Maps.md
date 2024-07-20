---
{"dg-publish":true,"permalink":"/1-cosmos/normal-maps/"}
---

202407200352
Status: #idea
Tags: [[Computer Graphics\|Computer Graphics]]
State: #nascient
# Normal Maps

They are a way to add detailed geometry visually, without actually adding more polygons to the mesh.
A good example is the following render which has jagged epaulets and armor (low poly mesh) with highly detailed looking curves and engravings.
![Pasted image 20230729162419.png|[Shader Basics, Blending & Textures • Shaders for Game Devs [Part 1](/img/user/The%20Vault/Media/Pasted%20image%2020230729162419.png)
VS what the mesh probably looks like.
![Pasted image 20230729162642.png](/img/user/The%20Vault/Media/Pasted%20image%2020230729162642.png)

A pretty common workflow for normal maps is to create a high poly model of a given model, export the normal map from the software, and then using it on a low poly model.

## References
