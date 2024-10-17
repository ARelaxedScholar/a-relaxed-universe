---
{"dg-publish":true,"permalink":"/1-cosmos/shaders/"}
---

202407200353
Status: #idea
Tags: [[Computer Graphics\|Computer Graphics]]
State: #nascient
# Shaders

Basically code running in the GPU that tells it what to render to the screen. They are not related in any way to [[Textures \|textures]], but they can use them.

Shaders can be used for a shit-ton of things, but one example would be layer effects.
 
Shaders are pretty amazing because of how specific and minute you can be with them. This image would be a paint to draw with only particle effects.
![[Pasted image 20230729161557.png\|[Shader Basics, Blending & Textures • Shaders for Game Devs [Part 1] - YouTube](https://www.youtube.com/watch?v=kf]]

## How to Make Shaders?
This will obviously vary depending which architecture, framework, or whatever we're writing.

Shaders have multiple properties some explicit like colors, values (ie: HP-values or time), textures and other implicit, like Meshes and Matrix4. 

In this case the difference between explicit and implicit is that explicit is specified in the shader code (written in shader language), while the implicit is figured out by the shader based on what object it's trying to render.

But the gist, is we will have to write a [[1. Cosmos/Vertex Shader\|vertex shader]] and a [[1. Cosmos/Fragment Shader\|fragment shader]] for any shader program we want to write. We will use a shading language to code our shaders, in my current case GLSL.

## Fresnel Shaders?
Ubiquitous. As something is facing away from you, the stronger the light. In effect, looks like an outline effect. 
![[Pasted image 20230729163002.png\|Pasted image 20230729163002.png]]
![[Pasted image 20230729163125.png\|Pasted image 20230729163125.png]]You can better see in this image how the things that are pointing in our direction (on the fatty) are a dark-unlit blue, while as we approach curves and thus sutff not directly towards us, light gets brighter.

This is based on the [[Fresnel Effect\|Fresnel Effect]].

## Other really interesting examples of Shaders
![[Pasted image 20230729163717.png\|Pasted image 20230729163717.png]]
**Return of Obra Dinn** - Only two colors with dithering helping to blend the gap between the harsh white and the somber ocre.

![[Pasted image 20230729163817.png\|Pasted image 20230729163817.png]]
**Kentucker Route 0** - Depth fuckery, look at the bird which is both in front and behind a tree.

![[Pasted image 20230729164258.png\|Pasted image 20230729164258.png]]
**The Portal Loccomotion** Renders both the inside of another room (where you're gonna portal) and the room you're standing in at once. This was done using shaders.

![[Pasted image 20230729164412.png\|Pasted image 20230729164412.png]]
![[Pasted image 20230729164506.png\|Pasted image 20230729164506.png]]
The flame is 2 quads, besides the particles. Everything is animated with shaders.

![[Pasted image 20230729164627.png\|Pasted image 20230729164627.png]]
Also just look **Uncharted** videos.



## References
