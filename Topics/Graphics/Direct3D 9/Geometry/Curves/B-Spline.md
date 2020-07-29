---
uid: bb64ed8a-0e2b-4278-bb2d-2c65dc0dce34
---

# B-Spline

![](~/img/B-Spline-Open.png "")   
*An open B-Spline does not go through its control points*  

![](~/img/B-Spline-Clamped.png "")   


*A clamped B-Spline which at least goes through its first and last control point*  



B-Spline is short for "basis spline".  

**Characteristics**  
* they do not go through their control points  
* they have C2 continuity!  
* they are a special case of NURBS  

* in order to have a sharp corner in a B-Spline it takes three control-points at the same position  
* it is hard to insert a control point without changing the curve  
* it is hard to make a straight line  
* depending on its degree, changing one point changes large parts of the curve  
* they cannot exactly describe circles and ellipses.  

In order to make it more intuitive to handle a B-Spline can also be constructed in a way it at least goes through its first and last control point.  

#### Related nodes
<span class="node">B-Spline (Value)</span>  
<span class="node">B-Spline (2d)</span>  
<span class="node">B-Spline (3d)</span>  
<span class="node">B-Spline (3d Wryly)</span>  

**See also:**  
* <a href="https://en.wikipedia.org/wiki/B-spline" class="extURL" target="_blank">Wikipedia on B-Splines</a>  



