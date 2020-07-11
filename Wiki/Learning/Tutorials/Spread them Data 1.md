---
uid: e9d19f29-9c2b-4afb-9386-f98318d4bfba
---

# Spread them Data 1
The following tutorial assumes that you have already worked through tutorial II: [Herr Inspektor](TODO INTERNALLINK:Tutorial Inspektor).  

# Spread them Data
If one day you decide to take the challenge and attend the final exam to receive the darkgray patcher needle you better be sure of having understood the ease of spreads. Read on carefully and you'll love it. Because:  

>In almost all cases where you want to deal with multiple instances of data, be it values, colors, files, textures, geometries... you can keep your patch pretty simple by thinking in spreads.  

# A Spread of Slices
First of all. The word *Spread* actually denotes nothing more than a list. A list of arbitrary data. Be it *values*, *strings*, *colors*,... and one of the entries in such a list we call a *Slice*.   

You are already aware that each of a node's pin is of one of vvvv's datatypes (i.e. value, string, color, enum, node). What has not been  mentioned so far is that every pin does not necessarily only hold one instance of the data it refers to, but potentially carries a whole spread of data.  

# Spread generators
You can find out the number of slices a pin has by hovering above it with the mouse. Create a <span class="node">LinearSpread (Spreads)</span> and hover above its output pin. Nothing special. Right. Now set the nodes *SpreadCount* to 5. Hover the pin again and note the (5) behind the value.   

![](~/img/linear1.png "") ![](~/img/linear5.png "")  

So the tooltip wants to make you believe that there are 5 slices but only shows you one. Be glad. Suppose you don't have only 5 but say 9874 slices. You wouldn't want to view them all in a tooltip. But of course there are other ways of viewing all the slices of a spread. Remember it from the last tutorial? When viewing a node in the Inspektor you can click the little arrows left to a pins name to get a view on the whole spread.  

![](~/img/sliceview.png "")  

Like the <span class="node">LinearSpread (Spreads)</span> node there are several more nodes that can generate spreads. If you are curious just quickly go over the HelpPatches of <span class="node">CircularSpread (Spreads)</span>, <span class="node">RandomSpread (Spreads)</span> and <span class="node">I (Spreads)</span>.  

# Making use of Spreads
Think further. There is a pin carrying a spread of 5 slices. How does a node deal with that spread if it is connected to one of its inputs. To see what happens you need to create <span class="node">Renderer (GDI)</span> and a <span class="node">Point (GDI)</span> that you connect to the renderer. This results in one + painted in the middle (i.e. at the coordinates given through the *X* and *Y* inputs at the <span class="node">Point (GDI)</span>) of the <span class="node">Renderer (GDI)</span>. Now Connect the <span class="node">LinearSpread (Spreads)</span> output to the *X* input of the <span class="node">Point (GDI)</span> and lean back.   

![](~/img/spreadpoint.jpg "")  

What you see is the clever <span class="node">Point (GDI)</span> node handling a spread. It simply paints its + not only once but 5 times since it got a list of 5 coordinates where to paint. Obvious, eh? If you were a point what'd you do? Yeah, but what if you get connected a spread with a different count on another pin. Duplicate the <span class="node">LinearSpread (Spreads)</span> set its SpreadCount to 2 and connect it to the *Y* input of the <span class="node">Point (GDI)</span> to see its reaction.   

![](~/img/doublespreadpoint.jpg "")  

Get that? The <span class="node">Point (GDI)</span> receives 5 values on the *X* input and 2 values on the *Y* input. What it does:   
* when painting the first + it takes the first slice of the X pin and the first slice of the Y pin  
* when painting the second + it takes the second slice of the X pin and the second slice of the Y pin  
* when painting the third + it takes the third slice of the X pin and since there is no third slice on the Y pin it simply take the first slice again  
* ...  

That's it. That is the way every node deals with spreads from its inputs. If the input understands spreads. If it doesn't all slices but the first will be discarded. To find out if a pin understands spreads watch it in the Inspektor. A > or >> left to its name indicates that it does understand spreads.   

It can never hurt to watch [the](https://vvvv.org/tiki-index.php?page=Video+Tutorials#Tutorial_9_Spreads_and_Slices) video tutorial] about spreads.  

# Accessing individual Slices
If you do it right, in most cases you'll not need to deal with individual slices, since almost every node can deal with spreads natively. But of course there are good reasons to access individual slices. Suppose we have such a reason and want to manipulate the 3rd slice that comes out of our first <span class="node">LinearSpread (Spreads)</span> manually. Therefore we insert a <span class="node">SetSlice (Spreads)</span> node as shown below.  
 
![](~/img/setslices.jpg "")  

The rightmost input of <span class="node">SetSlice (Spreads)</span> tells the node which slice we want to modify. Since slices are counted from 0, if we want to change the 3rd slice we have to enter 2 here. The 2nd input is the new value for that slice. Manipulate that value and note the 3rd + moving independently from the others.   

That's quite nice you may say. But have a look at this:  
![](~/img/setslicesadvanced.jpg "")  

Via the <span class="node">I (Spreads)</span> node we tell the <span class="node">SetSlice (Spreads)</span> that we do not only want to manipulate the 3rd slice but all slices from the first to the third. And with another <span class="node">LinearSpread (Spreads)</span> we create those 3 values...  

And so on. Thus, whenever you think things won't work out a spread will come handy.   

# Further experimenting
At this point you may also want to have a look at the [helppatches](TODO INTERNALLINK:HowTo Find Help) of: <span class="node">GetSlice (Spreads)</span>, <span class="node">Stallone (Spreads)</span>, <span class="node">Queue (Spreads)</span> and <span class="node">Cons (Spreads)</span>.  

The tutorial series now goes on telling you some things you should know about ((Tutorial IOBoxes|IOBoxes))