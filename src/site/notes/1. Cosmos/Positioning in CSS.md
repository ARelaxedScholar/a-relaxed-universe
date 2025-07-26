---
{"dg-publish":true,"permalink":"/1-cosmos/positioning-in-css/","created":"2025-06-16T13:17:43.353-04:00","updated":"2025-06-19T18:25:44.694-04:00"}
---

202506161317
Status: #idea
Tags: [[Web Development\|Web Development]], [[CSS\|CSS]] 
State: #nascient
# Positioning in CSS
There was a point in time where positioning in CSS was a pain. I'd imagine you'd  have to use tables extensively to design page as that is the only thing I can think of that would igve you a precise enough availability for layering.

While people with more experience with more experience than me might vouch for the use of tables,  for layout (I never tried.) It is clear that today, it'ss utility has been entirely superseded by the [[Grid layout\|Grid layout]].

There are as far as I am aware, five main tools for position:
- position: static; This is the default. Nothing special is done, and the element will just display wherever it should display based on its display type (block, inline, etc.) and its position in the document.
- position: absolute; which removes an element from the natural flow of the document and allows you to place your element wherever you want within the containing document. You'll control where exactly by defining the distance of the element from the top, bottom, left and right of the containing element (not too dissimilar to margins, but inner.) It also unlocks the use of the z-index, which allows you to define layer order, the higher the z-index, the closer you are to the front.
- position: relative; this relative is extremely confusing, until you realize relative means relative to itself! Instead of leaving the natural flow like position: absolute does, position: relative keeps the element in flow, but the top, left, right, etc. readjust the position of the element relative to where it would have been **in the natural flow**. So if you want to make text consistently higher, or lower than other text (say superscript, subscript) combining some relative positioning, with font-sizing is exactly what you'd want.



## References