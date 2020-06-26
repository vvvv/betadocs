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

 