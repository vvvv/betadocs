---
uid: b6b57a8e-98c9-4746-8519-ad0d9c651647
---

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




