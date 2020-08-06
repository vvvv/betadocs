---
uid: e8930bcb-0d6e-4dcd-8043-307641808fd9
---

## Creating Spreads

![](~/img/Spreads_ColsAndRows_Output2.png "")  

#### Manually
See [Viewing and Editing Spreads](xref:74099114-2128-4ce8-8935-42a669c0d52f#spreads-in-the-inspektor).  

#### Generative
See [Spread Generators](xref:fe02ed4b-7090-486b-9a1d-95067a5671d2).  


## Spreads as Inputs
For most nodes it can be said that the slice count on its output pins is directly defined by the slice count of its inputs. This is easy to grasp when a node's input all have the same slice count.  
![](~/img/EqualSliceCounts5.png "")  
When a node's inputs have different slice counts what happens is this: The output slice count is defined as the maximum of its input's slicecounts. When accessing slices of inputs that have a lower count the index is taken modulo its own count resulting in a repeated access of only the slices that are available.  

If any of a node's inputs is [NIL](xref:a2b935e8-17cd-4c26-b701-4919803792d1#nil), its output also returns nil.   
![](~/img/DifferentSliceCounts6.png "")