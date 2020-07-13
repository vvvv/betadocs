---
uid: 6cdb7263-e6b9-4adf-bb31-5a9b958d42c7
---

# Angles in 2D




# Rotations & Angles In General

![](~/img/circlecopy.jpg "")  

The most important fact about rotations is that you cannot separate a rotation with an angle of - lets say - 90° from a rotation with an angle of 360°+90° or from a rotation with an angle of 360°+360°+90°...  

All these angles result in the same rotation when applied to a transformation of a particle.  

Maybe you would then just say to yourself: "Ok then, let's just use rotations from 0° to 360°". However sometimes it is very usefull to know that e.g. 353° and 7° are in fact very near together.   

This is more obvious when you just compare the two angles 353° and 360°+7°=367°  
  
  367° - 353° = 14°
  
When you compare these values by subtracting them from each other you see that they are just 14° apart from each other.  

Just keep in mind that angles of any degree make sense (not only those between 0° and 360°) and are valuable to work with (like 367° in our case). We will make benefit from that later.  






# Rotations & Angles In vvvv

![](~/img/fraction_2007.04.2015.14.54.jpg "")  
[fraction.v4p](https://vvvv.org/tiki-download_file.php?fileId=1124)  

In vvvv all angles are measured in fractions of full cycles. That means that 360° equals a vvvv angle of 1.   

these angles all result in the same rotation:  
 0° = 0 cycles
 360° = 1 cycle
 720° = 2 cylces

these angles result in different rotations:  
 90° = 0.25 cycles
 180° = 0.5 cycles
 270° = 0.75 cycles

Again: When thinking of an object rotated by a certain angle, we at first aren't interested in the cyclecount of that angle, because adding or subtracting full cylces have no influence on the rotation. But we are only interested in the **Fraction** of a full cycle.  

To get the fraction of an angle in vvvv, use the <span class="node">Frac (Value)</span>. The Whole Part will give you the full clycles, the Real Part will give you the fraction of a full cycle.  






# Checking Angles For Equality

![](~/img/test_2007.04.2015.45.47.jpg "")  
*A rotation of 0.02 equals a rotation of 7.02*  

Since only the fractional part of an angle is responsible for the rotation, many different angles, which only differ in the amount of cycles, can be considered to be the same.  

To check equality of two angles use the <span class="node">= (Value Cyclic)</span>.  




# The Angle between Two Angles


To calculate the difference between two angles use the <span class="node">- (Value Cyclic)</span>.  




# The Shortest Way To Another Angle / The Cyclic Pin

![](~/img/cyclicanimation_2007.04.2016.21.59.jpg "")  
[cyclic animation.v4p](https://vvvv.org/tiki-download_file.php?fileId=1127)  

In animations it is quite useful to make use of the Cyclic Pin of your filter node. All the filters are programmed to behave most lazy when the Cylcic Pin is turned on.  

And with filter nodes i mean:  
* Damper  
* LinearFilter  
* Newton  
* Oscillator  
* DeNiro  

A more mathematical approach to say the same:   
With the cyclic pin you can change the toplogy of the space filters are acting in.   
They act in linear space (Cyclic Pin OFF) or in cyclic space (Cyclic Pin ON).  

Note that even if you plan to use just angles between 0...1, the cyclic pin will be your friend. The filters just know that angles of 0.01 and 0.99 are very near to each other...   





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




# Conversions From/To Radians And Degrees


### Related Nodes
<span class="node">Cycles (Value Degrees)</span>  
<span class="node">Cycles (Value Radians)</span>  
<span class="node">Degrees (Value Cycles)</span>  
<span class="node">Degrees (Value Radians)</span>  
<span class="node">Pi (Value)</span>  
<span class="node">Radians (Value Cycles)</span>  
<span class="node">Radians (Value Degrees)</span>  

To convert Degrees into vvvv angles:  
  divide by 360

To convert vvvv angles into Degrees:  
  multiply by 360


To convert Radians into vvvv angles:  
  divide by 2*Pi

To convert vvvv angles into Radians:  
  multiply by 2*Pi


To convert Radians into Degrees:  
  map the values from 0...2*Pi to 0...360 (map node)

To convert Degrees into Radians:  
  map the values from 0...360 to 0...2*Pi (map node)

In some special low level nodes, which are really thought to be direct implementations of math functions, we decided to use the unit radian (rad on your calculator), because this is the unit which is used in most other languages as well. In this way it is easier to implement algorithms which are already formulated in a peace of code (in one of these typical textual languages).  

 