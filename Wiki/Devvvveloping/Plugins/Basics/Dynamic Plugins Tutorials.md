---
uid: d19c0f1e-5133-4901-bdf6-fe62607cf45d
---

# Dynamic Plugins Tutorials
***under construction***  

# Introduction

You already are familiar with what a [dynamic plugin](TODO INTERNALLINK:Dynamic Plugins) is. We now examine how to code some simple dynamic plugins in c#.  

# Beginner
## #1 - Adding an If - Statement
A very common example is a node that handles some logic or that can be configured or just can be disabled.  

Let's say we want to write a node that randomly increases/decreases its output value, which could be used to simulate the movement of an insect. At any time we want to be able to put it to sleep. And we want to be able to change the vividness.  

So please clone with me the <span class="node">Template (Value)</span> and give the name "RandomWalker" or something like that.  

### The Random Behaviour
Behind   
```  
FOutput.SliceCount = SpreadMax;
```  
write the folowing:  
```  
var r = new Random();
```  
This creates a random generator and assignes it to a local variable which we just called "r".  
If you later on write "r." you see which methods can be called on the random generator. Use the keyboard arrow keys and move over "r.NextDouble".   
In the tool tip you can see that r.NextDouble will generate values between 0.0 and 1.0.   
Now change the line within the for-loop to:  
```  
FOutput[i] = (r.NextDouble()-0.5)*FInput[i];
```  
In the tool tip we saw that r.NextDouble will generate values between 0.0 and 1.0. Subtracting by 0.5 will result in a value around 0. So 50% it will be negative (walk left), 50% it will be positive (walk right). Multiplying with the input gives the ability to scale the random walking at any time. But still this is only the walking velocity. The position doesn't change yet.  
Now change the "=" in that line to to "+=", which means that the value of the last frame is changed by the random amount. Now it walks off...  
>note:  
Don't forget to use CTRL-S to save and compile.  
  
Delete the "logger" stuff by hitting CTRL-D. You deleted the wrong line? Undo (CTRL-Z) is your friend.  
Your code should now look like this:  
```  
public void Evaluate(int SpreadMax)  
{  
	FOutput.SliceCount = SpreadMax;

	var r = new Random();
						
	for (int i = 0; i < SpreadMax; i++)
		FOutput[i] += (r.NextDouble()-0.5)*FInput[i];	
}  

```  

### Sleep
Create a new Input by opening the region "fields & pins" and adding the following line behind the first input declaration:  
```  
[Input("Enabled", DefaultValue = 1.0, IsSingle = true)]  
ISpread<bool> FEnabled;
```  
After hitting CTRL-S you will see the new pin.  
Note that it is   
* called "Enabled"   
* accepts 0 or 1 (because it is a boolean)  
* it true (1.0) by default  
* and is not spreadable (IsSingle = true).  

Add   
```  
if (FEnabled[0])
```  
before your for-loop and the for loop will only be evaluated if "Enabled" is true.   
Please always indent your code by using TABs to make the structure of the code more visible.   

```  
if (FEnabled[0])  
	for (int i = 0; i < SpreadMax; i++)
		FOutput[i] += (r.NextDouble()-0.5)*FInput[i];
```

Note that the above is a shorthand for writing:  
```  
if (FEnabled[0])  
{  
	for (int i = 0; i < SpreadMax; i++)
	{
		FOutput[i] += (r.NextDouble()-0.5)*FInput[i];
	}
}
```  
As soon as you want to do more in your loop or more is dependant on if Enabled = true, you will need the code blocks anyway.  

## Ideas for more tutorials
1. Dealing with several Input Spreads
1. Dealing with several Outputs 
1. Working with Strings
1. Working with Colors
1. Working with Enumerations
1. How to write readable Code (1)
1. How to share a Dynamic Plugin
1. Working with Spreads of Spreads
1. Working with your own Data Type
1. Working with Transformations
1. Working with External Libraries 