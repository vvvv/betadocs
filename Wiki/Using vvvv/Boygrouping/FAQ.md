---
uid: d13e8bc8-1fe1-4a85-92ac-a6911ae00455
---

# FAQ


**Why does CTRL-B not work?**  


This shortcut only works in server-mode.   
Start vvvv with the /server flag to enable boygrouping.  




**It seems that bangs are not arriving on clients randomly?!**  

![](~/img/Boygrouping-TransmittingValues2.png "")   



Yep, that is very likely so. The solution to this problem is simple: Instead of having a bang between a blue and a gray node patch it so you have only a changing value (e.g. counting up a value) being transmitted via the network. The first blue node is then a <span class="node">Change (Animation)</span> to convert the valuechange to your desired bang.   

For an explanation read on: server and clients are not framesynced. It is most likely that clients run faster than the server, which usually has some overhead. Even though the *bang* will definitely be sent from the server it may just arrive on clients in between frames and be discarded. A bang is essentially a change to 1 followed by a change back to 0 in the next frame. If both those messages arrive on the client in the same frame only the last message is taken resulting in a loss of the bang.   



**Which network ports does Boygrouping use?**  

Per default vvvv establishes a TCP connection on port 3333 to every client for transmitting all graph changes.  

All value changes are being broadcast on UDP port 3333.   

You can change that default port via the <span class="node">Boygroup (VVVV Server)</span> nodes <span class="pin">Network Port</span>. Note though, that if you do so you also have to start your clients with a modified startup command like this:  
 /client 192.168.0.100:4444
