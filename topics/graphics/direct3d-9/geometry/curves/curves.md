---
uid: 6b7607ae-e850-42fc-84f7-34ba766c793e
---

# Curves
In mathematics a *Curve* is "a line that does not need to be straight". With that definition a large number of <a href="https://en.wikipedia.org/wiki/List_of_curves" class="extURL" target="_blank">different curves exist</a> each of which can be described by a mathematical formula.  

![](~/img/DifferentCurves1.png "")   
*Different mathematical curves*  

In computer graphics we're most interested in curves that can be described by mathematical formulas that are called <a href="http://www.mathsisfun.com/algebra/polynomials.html" class="extURL" target="_blank">polynomial functions</a>. In order to be able to draw arbitrarily curved lines often multiple such curve-segments are combined to a *Spline*. The term "Spline" originates from an old draftsmen tool called a <a href="https://en.wikipedia.org/wiki/Flat_spline" class="extURL" target="_blank">Flat Spline</a>.  


![](~/img/CurvesAndSegments2.png "")   
*Curves that are piecewise defined by polynomial functions are called Splines*  

There are many different types of splines (hermite, bézier, catmull-rom, b-spline,..). but they all share the following key properties:  
* they are continuous at the *Knots*  
* *Control Points* influence their shape  

![](~/img/BezierAndB-Spline_ControlPoints2.png "")   
*Splines with their segments, control points and knots*  

---  
Sources  
* https://en.wikipedia.org/wiki/Curve  
* https://en.wikipedia.org/wiki/List_of_curves  
* https://en.wikipedia.org/wiki/Spline_%28mathematics%29  
* http://pomax.github.io/bezierinfo
