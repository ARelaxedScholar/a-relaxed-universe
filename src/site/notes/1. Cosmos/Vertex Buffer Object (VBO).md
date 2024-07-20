---
{"dg-publish":true,"permalink":"/1-cosmos/vertex-buffer-object-vbo/"}
---

202407200353
Status: #idea
Tags: [[Computer Graphics\|Computer Graphics]]
State: #nascient
# Vertex Buffer Object (VBO)

The components that make up the attributes of a [[1. Cosmos/Vertex Array Objects (VAO)\|Vertex Array Objects (VAO)]]. 

## Why Vertex Buffer Objects?
This is a good question. Why not simply send each vertex to draw to the CPU, one by one? The answer is fairly simple. Performance. Sending info from the CPU to the GPU is fairly slow, and sending one by one all the vertices needed to create even the most basic scene would be hell and likely take ages. VBOs allow us to pack all that information into one [[1. Cosmos/Vertex Array Objects (VAO)\|VAO]] and send the VAO to draw to the CPU. This might be called [[Batching\|batching]], but I do not know for sure yet.

## And what about Element Buffer Objects (EBO)?

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/1-cosmos/element-buffer-objects-ebo/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




202407200352
Status: #idea
Tags: [[Computer Graphics\|Computer Graphics]]
State: #nascient
# Element Buffer Objects (EBO)

They are essentially buffers of indices. Why, though? Fairly simple, imagine you want to draw a square. Since computer graphics runs on triangles, you cannot just draw a square, instead you'd draw two triangles. Let's call them from Bottom-Right->Top Right->Top-Left->Bottom-Left, 1->2->3->4. In order to draw the square one would need to draw one triangle at (1-2-3), and then a second at (1-3-4).  See how two of the six vertices (total number) used are reused (ie: 1,3)? With VBOs, you'd need to define both triangles individually and then draw both. Which would lead to waste; this waste would only grow worse as models grow complex. Instead with EBOs we are allowed to define the vertices as only the unique vertices (1-2-3-4), and then specify a drawing order.

In other terms, with VBOs only:
I have one triangle at (1-2-3)
and another at (1-3-4)
and for BOTH I created vertices.

With EBO:
I have 4 vertices total (1-2-3-4),
and for each triangle I specify to OpenGL, draw a triangle using (1-2-3) and (1-3-4). It might sound trivial, but the difference is that in the first case, OpenGL actively created 2 extraneous vertices which don't provide anything to the final image. While in the second case, we only have as much vertices as required.



## References


</div></div>

#incomplete 

## References
