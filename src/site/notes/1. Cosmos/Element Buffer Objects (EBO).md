---
{"dg-publish":true,"permalink":"/1-cosmos/element-buffer-objects-ebo/","created":"2024-08-31T23:47:14.910-04:00","updated":"2024-07-20T03:52:17.274-04:00"}
---

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
