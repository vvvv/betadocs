---
uid: e87fb3bc-1512-456a-9529-8b901f459dc6
---

# Introduction
So you have just started vvvv for the first time and wonder how to proceed in learning, how to achieve some useful things with it. Take your time and read on. Within 20 minutes you should be through the first tutorial and have a basic understanding of vvvv.   

## Ready. Set. Go.
To see an example of what a vvvv project looks like, open the start_with_demo.bat file located in your vvvv directory. Once you have been suitably impressed by the demo, close vvvv by pressing the standard Windows shortcut for closing programms: ALT+F4. You might then be asked if you wish to save your changes. Just click *Don't save and Close* for now.  

Start vvvv again, this time using vvvv.exe. All you see is a virgin gray window, a so called Patch. Welcome to vvvv.  

Also see the video tutorial: [Starting](https://vvvv.org/tiki-index.php?page=Video+Tutorials#Tutorial_1_Starting_vvvv_for_the_first_time) vvvv for the first time]  

![](~/img/virgin_1.png "")  

## Preface
vvvv uses graphical objects for programming instead of a textual programming interface. Programs are created within patches. Individual operations or functions are represented as nodes. Connections between are called links and are drawn and modified with the mouse, creating a structure that sends data from one node to another.  

![](~/img/node.png "")  

Basically a node either generates, processes or outputs data. Some nodes even do a combination of those three operations. Every node can have several inputs and outputs which are represented by small black squares on its top and bottom which are called pins or inlets and outlets.  

In comparison to a textual programming language the input pins would represent the parameters/arguments of a function whereas the output pins would mean the result of that function.  

That much about the theory. Now let's go retro and say [Hello World](xref:eb717348-39dc-4687-a8d4-44db6c491c76) with the second tutorial.