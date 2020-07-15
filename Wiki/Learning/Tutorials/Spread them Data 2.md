---
uid: 5521e091-b068-4170-a28e-ea928208edb9
---

# Spread them Data 2
The following tutorial assumes that you have already worked through tutorial IV: [IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66).  

# Recall
Now that we've learned how to deal with IOBoxes let's have another look  at how nodes deal with spreads.   

![](~/img/spreadadd.png "")  

The two samples give you an idea what happens inside a node if it has to deal with spreads of different slicecount. Note that the first two and the last two graphs have the same result.  

>A node looks first at the slicecounts of all spreads it receives. The maximum slicecount of the inputs is used as the nodes output slicecount. Then the smaller inputspreads are internally resized to that slicecount. While filling up the new slices the existing slices are simply repeated.  

If that last paragraph confused you more than it helped you understand the subject. Well. Never mind. Often times simple things are hard to explain. If you've read this far you may have already understood the whole thing, even though you are not completely aware of it. Just quickly have a look at the next example.   


# Effortless handling of multiple Instances
Suppose you have a <span class="node">RoundRect (GDI)</span> linearly spreaded along its X coordinate and now you want every first rectangle be drawn green and every second drawn in red.   

![](~/img/rect2cols.jpg "")  

Now how would you go about having a grid of 5x5 rectangles? Your first thought may be to simply connect the <span class="node">LinearSpread (Spreads)</span> to the <span class="node">RoundRect (GDI)</span>s Y input. But see what happens:  

![](~/img/rectspreadhuh.jpg "")  

Still the <span class="node">RoundRect (GDI)</span> only draws itself only 5 times because the maximum slicecount on its inputs is still 5. The first X coordinate is the same as the first Y coordinate, second X is same as second Y and so on resulting in an ascending order.   

Thank vvvv there is a node, that comes in handy for the purpose of generating coordinates for a grid structure. Try the <span class="node">Cross (2D)</span> node as shown in the screenshot below.  

![](~/img/rectspreadcross.jpg "")  

<span class="node">Cross (2D)</span> outputs 25 slices for X and Y each which represent every possible combination of the input slices. Also note the distance between the rectangles can now be adjusted via the second input on the <span class="node">LinearSpread (Spreads)</span>.  

Finally let's add some interaction again. Say we want to know the distance of each rectangle to the mouse cursor. Again there is a node for such tasks: <span class="node">Points2Vector (2D)</span> gives you the distance between 2 points. Connect the node like shown below and guess what the 25 numbers in the bottom-right IOBox stand for.  

![](~/img/rectcrossandp2v.jpg "")  

Right. <span class="node">Points2Vector (2D)</span> is so neat and returns us the 25 distances of each of the grids points to the mouse coordinate.   
Now map those distances to a reasonable length so that we can use it as a size for the <span class="node">RoundRect (GDI)</span>s. Call it multimedia.   

![](~/img/rectcrossinteract.jpg "")  

Now adjust the Spreadcount of the <span class="node">LinearSpread (Spreads)</span> and you'll see: No matter how many rectangles you want to deal with, the patch stays as simple as on the first day.  

There are still some more things to know about spreads but for now you are released. Whenever you have the feeling you are missing some information browse the manual section on [Spreads](xref:00327d1e-65ba-4424-997d-615d9a469503) for additional details. 