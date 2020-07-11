---
uid: c83d235b-d906-4986-92dc-b309f4bb5da0
---

# Tricks With Cyclic Filters

![](~/img/lazy_quad_2007.04.2017.47.19.jpg "")  
[lazy_quad.v4p](https://vvvv.org/tiki-download_file.php?fileId=1128)  

![](~/img/laziest_quad_ever2_2007.04.2018.10.28.jpg "")  
[laziest_quad_ever2.v4p](https://vvvv.org/tiki-download_file.php?fileId=1129)  

Often basic geometric shapes are rotational symmetric.  
A plain quad e.g. can be rotated around 90°, 180°, 270°, ... and seems to haven't been touched.  
Also, you won't see a difference of a rectangle or a parallelogram and its copy, which is rotated about 180° (with center object = center of rotation).  

Again, all these different angles still have their right to coexist with us, but in a static snapshot you wouldn't be able to see a difference.  

We had this topic already with a factor of 360°. And we were only concerned about the fraction of full cycles.  
Let's try to extend that lazy cyclic behavior to fractions of half cycles or quarter cycles.  

Now lets say, we want to a have a most lazy animated quad.   

We again use a cyclic damper for that. But if it is rotated about 30° and it should go to 90°, in fact it should decide to rotate to 0°, because it will result in the same appearance like if it would rotate to 90°, but 0° is nearer to 30° than the specified 90°...  

The filter nodes however can only handle a cyclic mode with **full** cycles. So since there is no pin at our damper for specifying a quarter cycle, we have to trick a little bit: Lets use map nodes so that the damper treats quarter cycles as full cycles, does its cyclic animation, and after that use the full cycles of the damper and map them back to quarter cycles.  

* we think of our values as related to quarter cycles (0..0.25)  
* the damper needs values related to full cycles (0..1)  
 -> map 0..0.25 to 0..1

 -> damper on full cycles

* we need our original value range back  
 -> map back 0..1 to 0...25

It is used in here: [Draw](TODO INTERNALLINK:Draw).  


