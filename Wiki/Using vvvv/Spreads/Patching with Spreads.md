---
uid: e8930bcb-0d6e-4dcd-8043-307641808fd9
---

# Creating Spreads

![](~/img/Spreads_ColsAndRows_Output2.png "")  

#### Manually
See [Viewing and Editing Spreads](TODO INTERNALLINK:viewing-spreads#Spreads-in-the-Inspektor).  

#### Generative
See [Spread Generators](TODO INTERNALLINK:spread-generators).  


# Spreads as Inputs
For most nodes it can be said that the slice count on its output pins is directly defined by the slice count of its inputs. This is easy to grasp when a node's input all have the same slice count.  
![](~/img/EqualSliceCounts5.png "")  
When a node's inputs have different slice counts what happens is this: The output slice count is defined as the maximum of its input's slicecounts. When accessing slices of inputs that have a lower count the index is taken modulo its own count resulting in a repeated access of only the slices that are available.  

If any of a node's inputs is [nil](TODO INTERNALLINK:spread-definitions#nil), its output also returns nil.   
![](~/img/DifferentSliceCounts6.png "")