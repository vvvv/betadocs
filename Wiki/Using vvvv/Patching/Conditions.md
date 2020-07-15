---
uid: 69bdb72a-3e21-4b27-a4a6-c15e7c0ec56e
---

# Conditions
<span class="include">TODO INCLUDE patchingtoc</span>  

# Switch

![](~/img/Conditions-SwitchSimple.png "")  


#### Basic usage
In the most simplest scenario you want to switch between two inputs according to the result of some boolean operation (0 and 1).  

This is what the <span class="node"> Switch (Value Input)</span> is for.  

By default the Switch node has 2 inputs to switch between: in case of 0 <span class="pin">Input 1</span> and in case of 1 <span class="pin">Input 2</span>.  




![](~/img/Conditions-SwitchAdvanced.png "")   

#### More Inputs

The Switch node can accept any number of inputs to switch between by setting the <span class="pin">Input Count</span> via the Inspektor. The <span class="pin">Switch</span> input then takes an integer value ranging from 0 to Count-1 to switch between the inputs.  

#### See also
* If you want to apply a LERP (linear interpolation) between the inputs instead of switching between them have a look at <span class="node"> InputMorph (Value)</span>.  
* In order to switch Values according to a String, have a look at <span class="node"> Case (Value Input)</span>.  




![](~/img/Conditions-Spreads.png "")   


#### Spreads
Alternatively to switching between multiple individual values you can use the <span class="node">GetSlice (Spreads)</span> as shown to switch between the slices of a spread.  




# Boolean operations

![](~/img/Conditions-Booleans.png "")   


#### Boolean operations
There is no special Boolean datatype in vvvv. Boolean values are simply represented by 0 (false, off) and 1 (true, on). Use the following nodes for basic boolean operations:   
* <span class="node">AND (Boolean)</span>  
* <span class="node">OR (Boolean)</span>  
* <span class="node">NOT (Boolean)</span>  
* <span class="node">XOR (Boolean)</span>  

#### Relational operators
>, <, =,... return 0 or 1.  

#### State conditions
There are some special nodes that return a Boolean according to a change in state.   

Examples:  
* Detect if a value was changed: <span class="node">Change (Animation)</span>  
* Detect a change from 0 to 1 or 1 to 0: <span class="node">TogEdge (Animation)</span>  
* Toggle the output on and off by every bang on the input: <span class="node">Toggle (Animation)</span>  
* Set the output to 1 until there is a bang on Reset: <span class="node">FlipFlop (Animation)</span>  
* Set the output to 1 for a specified amount of time: <span class="node">MonoFlop (Animation)</span>  

See the helppatches of these nodes for details.  




# State Automatas

![](~/img/patching-automata.png "")  


When patching anything that can be separated into a series of states and events that cause transition from one state to another you are likely looking for <span class="node">Automata (Animation)</span>. Also the [Automata](xref:76f3717c-5da9-4a2a-9d53-4c5b982291a6#automata) has an automata built in.  

**See also:**  
* [Graphic Automata](xref:250959b9-c2b3-420e-ad36-0b7c6b784fb6)  





