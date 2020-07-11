---
uid: 307796da-69f5-46b0-a50b-8ae875f93b72
---

# Examples for declaring Pins using attributes
This is an Input Pin of type bool (ie. 0 or 1) with a hint to the GUI that it should be operated as a Bang. And it is Single which means it is not spreadeable.   
```  
[Input("Reset", IsBang = true, IsSingle = true)]  
ISpread<bool> FReset;  

```  
 
This is an Input Pin with minimun value 0.0 and maximum value 1.0. The Order attribute specifies the position of the pin in the node 0 will be left most 1 will be second pin from the left ...  
```  
[Input("Friction", MinValue = 0.0, MaxValue = 1.0, Order = 0)]  
ISpread<double> FFriction;  

```  

This is an Input pin called *My Input* with Variable name FInput of type int with a default value of 2. Remember that a pin can always be reset to its default using Alt+Rightclick on the pin.   

```  
[Input("My Input", DefaultValue = 2)]  
IDiffSpread<int> FInput;  

```  
Using [IDiffSpread](TODO INTERNALLINK:/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_IDiffSpread_1.htm) instead of ISpread allows you to check if the pins data has changed using the .IsChanged property:  

```  
if (FInput.IsChanged)   
{  
//do something   
}  

```  

This is a pin of type Vector2D whose x and y default values are both 0.0  
```  
[Input("Input", DefaultValues = new double[] {0.0, 0.0})]  
ISpread<Vector2D> FInput;  

```  

## PinGroup vs. BinSize
A PinGroup likge eg. used in <span class="node">Cons (Spreads)</span> that allows you to specify the number of inputs via a configuration pin in the Inspektor can be specified like:  
```  
[Input("Input", IsPinGroup = true)]  
ISpread<ISpread<double>> FInput;  

```  

If you do the same but leave out the *IsPinGroup = true* instead of the configuration pin that sets the pincount you'll get a *BinSize* pin:  
```  
[Input("Input")]  
ISpread<ISpread<double>> FInput;  

```  
 
More info: [pin attributes](TODO INTERNALLINK:pin attributes)  

# Dealing with SliceCount
Examples for getting and setting SliceCount:  

Get the Maximum spread count of any of the Input pins and set it to the Output pin.  
```  
FOutput.SliceCount = SpreadMax;  

```  
Get the SliceCount of a certain Pin   
```  
FInput.SliceCount  

```  

Get the maximum SliceCount of two Pins.  
```  
var count = FInput1.CombineWith(FInput);  
FOutput.SliceCount = count;  

```  

Get the minimum SliceCount from two pins.  
```  
var count = Math.Min(FInput.SliceCount, FInput1.SliceCount);  
FOutput.SliceCount = count;  

```  

# Spreads

## Playing with List&AssignFrom
<a href="http://msdn.microsoft.com/en-us/library/6sh2ey19.aspx" class="extURL" target="_blank">List</a> are a convinient way to play with dynamic spreads ,you can add , remove ,insert and much more...   
you need to add this : using System.Collections.Generic; to your code .  
There are many examples on the net you will find some nice ones in <a href="http://www.dotnetperls.com/list" class="extURL" target="_blank">dotnetperls</a>  

```  
   // we make a new list and called it myList 
      List<int> myList = new List<int>(); 


```  
We make some logic with it   
```  
 // If the Pin Add is Bang the spread from the Input Pin gets in .
			if (FAdd[0])
			{
			  myList.Clear();// We clear the List here to start all over otherwise we,ll add a new spread each time we bang .
				
             // Here we get the spread from Input Pin in 
			 // so loop as many times as the size of the spread to get it
				
			for (int i = 0; i < FInput.SliceCount; i++)
			  {
				myList.Add(FInput[i]);
			  }
				
			//here we add some more logic ,If spread contains the value in the filter pin 
			//we remove all occurances in the spread of this value.
			if (myList.Contains(FFilter[0]))
			  {
			myList.RemoveAll(item => item == FFilter[0]);
			  }
				
			// some more we want to add a value on top of the list and at the end 
			myList.Insert(0,111);
				// To the begginig of the List
				//Note this is the whole list so if you add again another one will be place
			myList.Add(111);// to the end of the List
			}	


```  

```  
// We clear the List if the Reset Pin is bang   
			if (FReset[0])
			{
				myList.Clear();
			}


```  
We Assing the List to our Output Pin   
```  
// we set the SliceCount of our Output pin to be the same as size of the List .  
			FOutput.SliceCount = myList.Count;
			//and Assign the data from our List to the Output Pin .
			FOutput.AssignFrom(myList); 


```  
 
This is the <a href="https://vvvv.org/contribution/code-snippetslistassignfrom" class="extURL contribution" target="_blank">Patch&Code</a> of it .   

Note : In most occasions will be more effective to use already in ISpread(T) Extension Methods instead of creating new list like    
```  
FInput.Add(FInput[i]) or FInput.RemoveAll(item => item == FFilter[0]);  


```  
instead of creating the new List and do    
```  
myList.Add(FInput[i])  
myList.RemoveAll(item => item == FFilter[0]);  

```