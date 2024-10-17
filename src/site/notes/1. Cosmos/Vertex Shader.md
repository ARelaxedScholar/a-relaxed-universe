---
{"dg-publish":true,"permalink":"/1-cosmos/vertex-shader/"}
---

202407200354
Status: #idea
Tags: [[Computer Graphics\|Computer Graphics]]
State: #nascient
# Vertex Shader

![[Pasted image 20230729171635.png\|Pasted image 20230729171635.png]]

It loops over all the vertices of a mesh, and then does stuff with it. Typically it will simply place the mesh, somewhere in the world based on vertex space and [[1. Cosmos/Normalized Device Coordinates (NDC)\|Normalized Device Coordinates (NDC)]]. Here placing the mesh is an abuse of language, it would likely be better to say that it reproduces the mesh in that vertex space by placing each vertices of the mesh individually. Note it can do much more than just that, like coloring the vertexes itself, but typically all the rest of the work is left to the fragment shader.

*Important: You don't need to specify these in NDC yourself. You will always be working in a coordinate system that makes sense to you (ie: pixels, meters, inches, etc.) and then through a matrix multiplication, the appropriate coordinates will be obtained. We pretty much always multiply position by the viewMatrix (our camera) and then by the projectionMatrix (what actually converts the stuff to NDC)*

The first multiplication will clip whatever doesn't fit in our camera, and the second will adjust the dimensions to clip space.

## Usages?
Everything really, but some specific stuff would be:
- The flow of water
- The rustling of leaves
- The dancing of a flame

## What do you do in it?
Typically only the placing of the vertices, and/or the passing of variables to the [[1. Cosmos/Fragment Shader\|fragment shader]].



## References
