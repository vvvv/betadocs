# West Tricks
---  
# Some Tips, Hints and Tricks we learned using VVVV...

This page is created for users that are past the new-bee status, and are ready to learn some nice hints, pointers and tricks to make their patching life a little easier.  

The contributions come from our proud members, and are maintained by West. So feel free to send in your clever ideas using [this thread](TODO INTERNALLINK:/tiki-view_forum_thread.php?comments_parentId=10623&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=7) in the forum.    

#  Keep Clean Structure In Patches

The biggest trap a VVVV user can step into when creating big and complicated patches is that they can become rather messy pretty quick.  

<span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span> has made a nice patch with great tips that will help to make your patches keep looking nice and clean. Things like marking not very important nodes white, or hiding, stretching nodes, and aligning them will be demonstrated. The usage of these methods is personal, some people hate to hide pins, others are very pleased with it.  

**Advantage:** You (and others) might understand the patch easier when they get opened a day later.  

**Download:** [Examples on how to keep clean structure in your patches.](TODO INTERNALLINK:/tiki-download_file.php?fileId=931)  

#  Difference between LFO and Integrate

The <span class="node">LFO (Animation)</span> node is very often used as the heart, or engine, for movement in Patches, most users overlook the similar, and in some cases even more powerful <span class="node">Integrate (Differential)</span> node.  

The <span class="node">LFO (Animation)</span> has some nice configuration pins that allows you to stop, reverse or even phase shift the output, which are very useful for time related events. On the other hand, <span class="node">Integrate (Differential)</span> lacks all these sweet pins, but has one very clear advantage over the LFO, and that is when you want to smoothly stop and reverse the output.   

The Position Time pin of the <span class="node">Integrate (Differential)</span> is the reciprocal (1/x) of the Period pin of the <span class="node">LFO (Animation)</span>, just be careful in using a time of 0, the LFO will go super fast, while the integral will come to a stop. Using the <span class="node">Frac (Value)</span> node, you can separate the Integrate output to make it look like LFO, or use a simple <span class="node">+ (Value)</span> to make an LFO output look like the Integrate output.  

**Download:** [Demonstration of the LFO and Integrate nodes.](TODO INTERNALLINK:/tiki-download_file.php?fileId=1871)  


#  Getting Highest Value of A Spread

When you have a spread of values and want to figure out what value is the highest, or the lowest, there is only one node you want to worry about, <span class="node">Bounds (Spectral)</span>.   

If you are also interested in what slice goes with that lowest, or highest value, there are a few ways to do that, but after examination of the [performance with CTRL + SHIFT + F9](TODO INTERNALLINK:/tiki-index.php?page=performance), the sort/car method was the most efficient. How ever, when you have a always changing spread, the bounds/sift combo is the way to go.  

**Advantage:** Clean and fast way to get the highest or lowest value from a spread.  

**Download:** [Example Patch To Get Highest Value.](TODO INTERNALLINK:/tiki-download_file.php?fileId=1864)  

# High Speed Counter

Sometimes you want a counter that counts very fast, you could use an <span class="node">LFO (Animation)</span>, <span class="node">Change (Animation)</span> and <span class="node">Counter (Animation)</span> combination, and set the period to an extreme low value.   

But by simply mapping, with the <span class="node">Map (Value)</span> node, the <span class="node">LFO (Animation)</span> node, you get a precise control about the length of time a counter needs to count from 1 to 100 (for example).    

**Advantage:** you can now count from 1 to 100 in exactly 2.1 seconds.  

**Download:** [Example Patch HighSpeedCounter.](TODO INTERNALLINK:/tiki-download_file.php?fileId=920)  

# Using Colors As Values

VVVV does not have that many nodes to deal with color. For example a simple **Switch (Color)** isn't there. (There is a <span class="node">InputMorph (Color)</span>, but this is just an example) To deal with this problem, I used  to use the [HSV (Color) Split](TODO INTERNALLINK:HSV (Color) Split) node, to split the color in its 4 values, than I would Applied 4 [Switch (Value) Input](TODO INTERNALLINK:Switch (Value) Input) nodes, and than I would combine the output again using the [HSV (Color) Join](TODO INTERNALLINK:HSV (Color) Join) node. Works great, but I do not like to use the same node 4 times.   

Using [Vector (4d) Join](TODO INTERNALLINK:Vector (4d) Join), just ONE switch, and a [Vector (4d) Split](TODO INTERNALLINK:Vector (4d) Split) node, I instantly used one node less.   

**Advantage:** you can now also do more complex stuff with colors, without copying the patch 4 times.   

**Download:** [Example Patch Using 4D Vector for colors.](TODO INTERNALLINK:/tiki-download_file.php?fileId=921)  

#  Switching direct with LFO

If you think that a [Switch (Value) Input](TODO INTERNALLINK:Switch (Value) Input) or any other switch only  switches when you set the switch pin to a correct value read on.  

Connecting the Cycles pin of an <span class="node">LFO (Animation)</span> node directly to a switch will also switch, on a time interval.  

**Advantage:** easy switch between values, and it saves some patching  

**Download:** [Example Patch using LFO cycle to switch.](TODO INTERNALLINK:/tiki-download_file.php?fileId=927)  

#  Using a Gamma node to correct a Damper output

Using a filter, like the <span class="node">Damper (Animation)</span> node, to create a 'fading tail' on a color spread is a very nice and easy way. Sometimes the results are not what you had in mind, and you spend much time to correct it and to make it look better.  

Using the <span class="node">Gamma (Value)</span> node, you can easy compensate and play with the tail, lower value gives a longer tail.  

**Advantage:** quick way to compensate the values after a filter.  

**Download:** [Example Patch to Use a Gamma Node to correct the Damper output.](TODO INTERNALLINK:/tiki-download_file.php?fileId=928)  

#  Create your graphical user interface using the intersect node.

Most people who are building patches soon want to create something like a GUI so also 'non VVVV people' can use their work.  

There are some ready to go buttons here on the website, like the ones user <span class="user"><a href="https://vvvv.org/users/Woei" class="extURL" target="_blank">Woei</a></span> node.  

There are 2 nodes in the current VVVV release,  Button (3d Quad) and Button (3d Mesh), created by <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>, it is worth it to check the helpfiles.  

**Advantage:** Anyone who can handle your interface can control your patches.  

**Download:** Check out the button patches off <span class="user"><a href="https://vvvv.org/users/woei" class="extURL" target="_blank">woei</a></span> and the  Button (3d Quad) and Button (3d Mesh) nodes.   

#  Force awareness of pressing a button

Sometimes a user isn't sure what button to press, so he presses all of them, very fast. Of course you only want your patch to react on buttons that the user seems to be aware of when pressing.  

<span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span> has written a way to make a button press only count when it is pressed a certain amount of time. And don't forget to check the very cool helpfile that comes with the patch.  

**Advantage:**  it switches to 1 only if the user made a decision longer than a certain time.  

**Download:** [Force user awareness when pressing a button.](TODO INTERNALLINK:/tiki-download_file.php?fileId=932)  
[The Helpfile.](TODO INTERNALLINK:/tiki-download_file.php?fileId=933) (place both in same folder)  

#  Measure the time between two events

It can be very handy sometimes to measure the time that is passed between two events (e.g. mouseclicks).  

<span class="user"><a href="https://vvvv.org/users/elektromeier" class="extURL" target="_blank">elektromeier</a></span> has made a nice solution, using a <span class="node">Stopwatch (Animation)</span> and <span class="node">S+H (Animation)</span> node. The trick is now to let the stopwatch run one vvvv frame longer before being reset, so the s+h node can get the latest time before this reset. This is where the <span class="node">FrameDelay (Animation)</span> is used for.  

**Advantage:** Get the time passed between two events.  

**Download:** [Measure the time between two events.](TODO INTERNALLINK:/tiki-download_file.php?fileId=934)  

#  Get your Values back after a Boolean operation.

After doing a <a href="http://en.wikipedia.org/wiki/Boolean" class="extURL" target="_blank">boolean</a> operation, like <span class="node">AND (Boolean)</span>, <span class="node">OR (Boolean)</span>, <span class="node">< (Value)</span> or <span class="node">= (Value)</span> with 2 spreads, you end up with a spread filled with '0' or/and '1'. Now, let us assume you are more interested in the values where these zeros and ones originated from.  

The <span class="node">Select (Value)</span> node is used for this.   

**Advantage:** Use the actual values from boolean operations.  

**Download:** [Example file on how to use the Select node after a Boolean.](TODO INTERNALLINK:/tiki-download_file.php?fileId=939)  

#  Have a Clipboard module

Collect Items you often need   
* IOboxes configured as fader  
* IOboxes with standard descriptive names like "Width" "Height" "SpreadCount" etc.  
* combinations of e.g. renderer,camera,group,axis and grid  

and put them all together in a patch.  
save this patch e.g. as Clipboard (VVVV) somewhere in your modules folder.  

now you are able to copy and paste your favourite "patchlets" wherever you want.  
just doubleclick for new node,   
start typing C-L-I- ,  
select clipboardpatch,   
copy all you need,   
CTRL-W to close clipboardpatch (there is no dialog because you didn't change anything),   
paste inside your patch.  


**Advantage:** saves a lot of time.  

**Download:** [Example for ClipboardPatch.](TODO INTERNALLINK:/tiki-download_file.php?fileId=948)  

>you could also use the "very basic help"-patch assuming that you don't need it anymore.  

**Advantage:** even faster! just hit F1 when nothing is selected.  

**Disadvantage:** when migrating with all your files between those fast changing beta versions you will for sure forget to copy that helpfile...  

#  Make helppatches not only for Modules

When you stick to the [Conventions.NodeAndPinNaming](TODO INTERNALLINK:Conventions.NodeAndPinNaming) you can make helppatches for almost everything:  
^a subpatch named **foobar.v4p** can have a patch **foobar help.v4p** located in the same folder.  

with F1 on that **foobar** node the helppatch is started.  

same for shaders and freeframe.dlls:  
**FooFoo.fx** can have a helpfile **FooFoo help.v4p**  
**FreeFree.dll** can have a helpfile **FreeFree help.v4p**  


#  Random Shuffle your Spreads

This is a nice little trick that lets you Shuffle the sequence of the slices in a spread at random.  

The trick that is used makes smart use of the 'former index' pin of the <span class="node">Sort (Spreads)</span> node. It sorts a random generated spread, and uses that former index to get the slices from the spread you want to shuffle (or mix), this results with your original spread, but now shuffled.  

**Advantage:** makes the outcome of most patches less predictable.  

**Download:** [Download the random shuffle module.](TODO INTERNALLINK:/tiki-download_file.php?fileId=978)  


#  Make your Random Spread more Random
I know that most of us, when they want to generate a random spread, connect the Cycles pin of an <span class="node">LFO (Animation)</span> node to the Random Seed pin of the <span class="node">RandomSpread (Spreads)</span> node.  

Most of us should have noticed that the outcome of two upcoming cycles is less random than we hoped. So why not make the Random Seed input random using a <span class="node">Random (Value)</span> node!!  

**Advantage:** The outcome of 2 random spreads is way more random.  

**Download:** [Small example on how to get a spread be less predictable.](TODO INTERNALLINK:/tiki-download_file.php?fileId=994)  


#  Rounding your Values Up or Down

One of the nodes that vvvv misses is a decent way to round your values up or down, in other words, make an integer out of a fraction that the fraction is closest to.  

Using the <span class="node">Frac (Value)</span> node, and a simple <span class="node">< (Value)</span> boolean operation, you can decide to what integer your fraction is closest to. In this demonstration module I also added a way to decide ho many decimals we want to use. How ever, the more easy way to do this, is by simply adding 0.5, using the <span class="node">+ (Value)</span> node before using the <span class="node">Frac (Value)</span> node. But this only works for rounding to an integer value.  

**Advantage:** Rounding up or down is useful for selecting slices with fractions in the slice index, sending data over using artnet, and much more I am sure.  

**Download:** [Rounding (Values).v4p (6.05 Kb) module.](TODO INTERNALLINK:/tiki-download_file.php?fileId=979)  
[Rounding (Values) help.v4p (5.21 Kb) helpfile.](TODO INTERNALLINK:/tiki-download_file.php?fileId=980)  


#  Build a simple Timeline for movement

Letting an object move along a path that you pre-directed was always high on my wishlist. I remember difficult patching with an [IOBox (Value) Advanced](TODO INTERNALLINK:IOBox (Value) Advanced) that need to be filled with values, <span class="node">GetSlice (Spreads)</span> nodes and dampers to make it smooth.  

The node <span class="node">B-Spline (Value)</span> is not designed for this, but works great, with an LFO and some values. Don't forget to change the 'input room' pin to 'normal 0..1'. Thanks to <span class="user"><a href="https://vvvv.org/users/gregsn" class="extURL" target="_blank">gregsn</a></span> for the idea.   

**Advantage:** This is the most easy and simple time-line I have come across.  

**Download:** [Example for a "Stupid" Timeline](TODO INTERNALLINK:/tiki-download_file.php?fileId=995).  


#  Make an LFO only run once

The <span class="node">LFO (animation)</span> is the motor for most patches. But sometimes you want that motor to run only once. I tried doing this with a complex way using a framedelay, and a toggle to set the LFO on pause when a cycle is passed. How ever, a framedelay gives a one frame delay, so the pause was always too late.  

Now I decided to let the LFO run just and switch to zero (or one if you desire) on a cycle change, works way better. You can start a 1 time run with simple bang.  

**Advantage:** Run an LFO exactly one time, and let it stop at exactly 0.0000 or 1.0000.  

**Download:** [Download an example to run an LFO for only one cycle.](TODO INTERNALLINK:/tiki-download_file.php?fileId=996)  


#  Don't confuse Change and TogEdge

When doing an action that depends on the change of a value, you can choose between the <span class="node">Change (Animation)</span> and <span class="node">TogEdge (Animation)</span> nodes.  

In most cases <span class="node">Change (Animation)</span> is the node of choice, however, in some cases it is better to pick the <span class="node">TogEdge (Animation)</span> node, especially when working with the [Keyboard (System) Global](TODO INTERNALLINK:Keyboard (System) Global). The TogEdge will only work for values that range from 0.0000 to 1.0000, and even worse, it rounds off the values internally to 0 or 1, whatever is closed. So a change from 0.3 to 0.4 will not produce a Bang, while a Change will.  

**Advantage:** Just Nice to know I thought.  

**Download:** [A patch that makes the difference a bit more clear.](TODO INTERNALLINK:/tiki-download_file.php?fileId=1009)  


#  Use the Decay to Visualize a Bang

When you have something that looks nice, and you want to give it something extra, or make it react to a beat, I had always a hard time  to that. Look at [Tonfilm Modules](TODO INTERNALLINK:tonfilm-Modules) for a simple beatdetector.  

Since most events produce a bang, most filters are not use able, so I always patched loads of complex stuff to generate something that I could use. But now I discovered a new trick, using the <span class="node">Decay (Animation)</span> node, sometimes combined with a <span class="node">Map (Value)</span> and a <span class="node">+ (Value)</span> or <span class="node">- (Value)</span>, and setting the attack time to 0 sec and the Decay time to whatever looks nice. I work with beatbangs, anything lower than 0.5 sec (=120 Beats per Minute) looks nice.  

**Advantage:** Nice and fast way to make patches Bang-reactive.  

**Download:** [Example how you can use this trick.](TODO INTERNALLINK:/tiki-download_file.php?fileId=1485)  


#  Make a One Pixel thick line or Point

When you want a small point or indicator, people tend to Scale down their Quads to very low values. The trouble with this begins when you have the <span class="node">Renderer (EX9)</span> in NOT full screen mode, or when you change the screen size. Size of an object is always relative to the actual renderer size.   

By using a small trick, you can make a <span class="node">Quad (DX9)</span> a point, or line with the size of 1 pixel, regardless of the screensize you are using.  
The node <span class="node">Fill (EX9.RenderState)</span> set to Point or Wireframe, depending if you need a point or a line, connected to a <span class="node">Quad (DX9)</span> with an X or Y scale of 0.0000 will make a nice 1 pixel point, or line.  

**Advantage:** The size of the <span class="node">Renderer (EX9)</span> doesn't matter, it is always 1 pixel.  

**Download:** [An example to create a 1 pixel point or line.](TODO INTERNALLINK:/tiki-download_file.php?fileId=1277)  


#  Quickest Way to make a spread with same values

To generate a spread, with all the same values, I know that most of us use a <span class="node">LinearSpread (Spreads)</span> and set the Input pin to the value they need, Width to 0, and the Spread Count to what they need. Well, using the <span class="node">Select (Value)</span> node, it saves you exactly one extra click, and we all want to patch faster.   

The only thing to worry about is connecting the correct outlet pin. This is also an easy way to create a Color <span class="node">Select (Color)</span> or String <span class="node">Select (String)</span> spread, with the same colors and strings.  

**Advantage:** Save patching time, and the node is smaller.  

**Download:** [Quick Example on how to use select node another way than is mentioned in the Helpfile.](TODO INTERNALLINK:/tiki-download_file.php?fileId=1486)  


 

#  Get Transparency out of the Renderer.

A lot of people are not aware that the <span class="node">renderer (EX9)</span> has a background, with a non transparent color, black by default. If you want to use the renderer as a texture on some other object, you can use <span class="node">DX9Texture (EX9.Texture)</span> for that.   

The Default texture format, "non specific", does not output an alpha. This node comes with a pin that is hidden, so you have to use Herr Inspector for that. When you change the "format"pin to another type off texture, any one that begins with an A (for alpha) will work.  

The next step is to make the background of the renderer transparent, use can use a <span class="node">Setalpha (Color)</span> for that.  

When you want to save a renderer as PNG file, this is the only correct way to do it. The node <span class="node">Writer (EX9.Texture)</span> is used for this purpose.  
 
**Advantage:** You can re use complicated renderers very easy. Or save them with transparency enabled.