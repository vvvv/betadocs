---
uid: d42a6b02-6d4b-4c6b-881f-2c4694a25721
---

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



