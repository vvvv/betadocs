---
uid: 1c796b9b-c238-4ebd-be0b-3350f9f1c5aa
---

# DMX Hardware


---  
# **Artnet** (a DMX-over-Ethernet Standard)
>there are *some* Artnet Interfaces which easily play with vvvv.  
they all have a big advantage: you don't need to install any drivers.  
vvvv includes two nodes for communication with Artnet:  
* <span class="node">DMX (Network Artnet Sender)</span>  
* <span class="node">DMX (Network Artnet Receiver)</span>   
but this is by far not the only advantage: visit [DMX.Artnet](TODO INTERNALLINK:DMX.Artnet) to find out more.  
for sure there are more products offering Artnet functionality but all devices listed below have been used with vvvv. basically every Artnet Devices should work with vvvv.  

## Artistic Licence Etherlynx
<a href="http://www.artisticlicence.com/index.php?mode=products&sub=overview&action=&category_id=4&product_id=393&project_id=&policies_id=&cart_id=&order_id=" class="extURL" target="_blank">Artistic Licence Etherlynx</a> offers 2 inputs and 4 outputs. <a href="http://www.artisticlicence.com" class="extURL" target="_blank">Artistic Licence</a> invented Artnet.  
## ELC dmXLAN node8
the <a href="http://www.elclighting.com/web/index.php?option=com_content&task=view&id=4&Itemid=4" class="extURL" target="_blank">ELC dmXLAN node8</a> even has 10 ports: 2 Inputs and 8 individually configurable ones. highly configurable with priority/backup solutions etc.  
## Enttec Datagate DE / DME
<a href="http://www.enttec.com/index.php?main_menu=Products&pn=70024&show=description&name=datagate" class="extURL" target="_blank">Enttec Datagate</a> offers **8** DMXUniverses individually configurable either as Input or Output. the routing engine of the DME version even allows to define complex routing rules. around 1000-1200 euros.  
## Enttec ODE (Open DMX Ethernet)
the <a href="http://www.enttec.com/index.php?main_menu=Products&pn=70305&show=description&name=ode" class="extURL" target="_blank">Enttec ODE</a> costs around 200 euros and offers 1 DMXUniverse configurable either as Input or Output. it is fast and reliable. only a little disadvantage: external power supply (wall wart...). but there is also a <a href="http://www.enttec.com/index.php?main_menu=Products&pn=70306&show=description&name=odewithpoe" class="extURL" target="_blank">POE (Power over Ethernet)</a> version avialable for around 250 euro.  
Don't forget to upgrade your <a href="http://www.enttec.com/index.php?main_menu=Products&pn=70306&show=firmware" class="extURL" target="_blank">firmware !!!</a>  
<span class="user"><a href="https://vvvv.org/users/Karistouf" class="extURL" target="_blank">Karistouf</a></span> writes:   
there is a deep bug inside the pic programmation that may completely block your artnet ode if you send artnet stream to it and you are configuring your ip adress at the same time.   
## MA 2port Node
you need a look at the user manual (or access to www...) to force the <a href="http://www.malighting.com" class="extURL" target="_blank">MA 2port Node</a> 'back' to Artnet. MA prefer using their own proprietary protocol MA-net.  
---  

# **USB Interfaces** 
## Cinetix USB/DMX-512 Control Box
<a href="http://cinetix.de/interface/english/index.htm" class="extURL" target="_blank">www.cinetix.de</a>. Interface can be controlled via virtual COM-Port/RS232. Modules for sending and reading DMX with the cinetix box can be found at <span class="user"><a href="https://vvvv.org/users/MSBERGER" class="extURL" target="_blank">MSBERGER</a></span>.   
## DMX4ALL USB-interfaces
The <a href="http://www.onlineshop.dmx4all.de/DMX4ALL-DMX-Interfaces:28.html" class="extURL" target="_blank">DMX4ALL USB Interfaces</a> are a family of DMX USB interfaces using a virtual COM-Port and a good documented protocol by <a href="http://www.dmx4all.de" class="extURL" target="_blank">DMX4ALL</a>.  
A module for these interfaces can be found here [module](TODO INTERNALLINK:msberger.Modules.Devices)  

## Enttec Open DMX USB
<span class="user"><a href="https://vvvv.org/users/catweasel" class="extURL" target="_blank">catweasel</a></span>.  
<span class="user"><a href="https://vvvv.org/users/Karistouf" class="extURL" target="_blank">Karistouf</a></span> writes: written a dmx engine named [((userpageKaristouf|little_cat] to receives thruth udp levels from vvvv. **vvvv can works with enttec open** and 4 more interfaces. now you can use an open ! ;-)   
## Enttec USB Pro
There is also the (bit more expensive) very fast Enttec USB Pro dongle. This DMX dongle can communicate with vvvv using a virtual COMport, user <span class="user"><a href="https://vvvv.org/users/west" class="extURL" target="_blank">west</a></span> had written two standalone exe for communicating with ENTTEC PRO (and other dmx interfaces) from vvvv:   
**[little_cat](https://vvvv.org/tiki-download_wiki_attachment.php?attId=199)** who receives udp string containing your values and send them to dmx devices  
**[little_mouse](https://vvvv.org/tiki-download_wiki_attachment.php?attId=204)** who receives dmx and convert it to an udp string you receive easely inside of vvvv. little_cat and little_mouse are working with ENTTEC PRO.  
## Enttec USB Pro Mk2
The latest of Enttec's fast DMX interfaces supports two dmx universes in parallel. Extending <span class="user"><a href="https://vvvv.org/users/west" class="extURL" target="_blank">west</a></span> wrote this patch to initialise and access both USB Pro MkII's universes.  
<a href="https://vvvv.org/contribution/enttec-dmx-usb-pro-mkii-module" class="extURL contribution" target="_blank">enttec-dmx-usb-pro-mkii-module</a>  
## RODIN1: USB to DMX, DMX transmitter
<a href="http://www.peperoni-light.de/products1.htm" class="extURL" target="_blank">www.peperoni-light.de</a> It's a really small DMX output device, running with a driver named DASHARD.DLL just like the USBDMX2 interface, so you can use the vvvv DMX output node. Apparently many more manufacturers sell products based on these drivers.   
## Soundlight USBDMX2
>**Caution: Current Version may NOT work with vvvv**  
see [this thread](https://vvvv.org/tiki-view_forum_thread.php?topics_offset=1&forumId=18&comments_parentId=17135) and also [this thread](https://vvvv.org/tiki-view_forum_thread.php?topics_offset=1&forumId=18&comments_parentId=20314) but maybe our fellow [karistouf](https://vvvv.org/tiki-index.php?page=Userpagekaristouf) has a solution ;)  
The <a href="http://www.pcdmx.de/gb/home.htm" class="extURL" target="_blank">USBDMX2 by Soundlight</a> was one of the most easy way to get DMX output from your computer. The interface has a sturdy case, simple USB in / DMX out operation, and three LEDs for quick diagnosis. It's quite affordable as well. After installing it's drivers you have to put a copy of **DASHARD.DLL** (which comes with the interface) into your vvvv folder (which contains the vvvv.exe). The node to get the interface running is <span class="node">DMX (Devices SoundLight USBDMX)</span>.   
---  

# **Ethernet** (not Artnet)
## LANBOX LCX
<a href="http://www.lanbox.com" class="extURL" target="_blank">www.lanbox.com</a>  
The Lanbox can be used with a UDP connection to send realtime DMX. The Lanbox is a very complex device and can be programmed to do amazing things in standalone mode. Think of a verry powerfull lighting console without any local control. TCP/IP, MIDI can be used to control the standalone features.  
There are modules by kalle and sebastian oschatz. It works pretty fine.  <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span> has another ~30 patches mostly useful for configuring the LANBOX for standalone usage, which is VERY COMPLEX.  
---  

# **RS232 etc.**
## Cinetix RS232/DMX-512 Control Box
<a href="http://cinetix.de/interface/english/index.htm" class="extURL" target="_blank">www.cinetix.de</a>.  
Probably one of the last real/native RS232-DMX-interfaces still available    
## DMX4ALL RS232 board (no longer available !)
The DMX4ALL is a simple and small board to convert RS232 to DMX.  
It can be used even without a built-in VVVV driver  as it is fully controlled via RS232. When considering the DMX4ALL sender kit there is an option to get a "ready soldered" PCB unit for +5 euro.   
so this would be 44,95 euro + power supply + housing + XLR 5 plug + shipping.  
<span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span> writes:   
Get yourself a rugged box (best from steel), integrate that PrintedCircuitBoard and a stable power supply, integrate all plugs you need.  
i highly recommend:  
* a good 9pin SubD with screws to lock  
* a Neutrik NAC3MPA for mains voltage   
* also for the power cable a Neutrik NAC3FCA lockable power connection.    
* BE SURE THAT YOUR BOX IS GROUNDED PROPERLY!  
* a 5pin female XLR (recommended --> Neutrik, the very best)  
* and perhaps a 3pin female XLR ( --> Neutrik...)  
you should get all those plugs at CONRAD Elektronik (normally on stock in the shop)  

If you act on this advice i am very sure that your DMX4all-device is failure-proof.  
Be sure that you don't have to control much more than 50 DMX channels because the performance of this device is not really that good.   
be sure to use V1.5 of DMX (Devices DMX4all.v4p) which can be downloaded at [kalle.Modules](TODO INTERNALLINK:kalle.Modules)   
patch your spreads to the input of that node and there you go.  

<span class="user"><a href="https://vvvv.org/users/MSBERGER" class="extURL" target="_blank">MSBERGER</a></span> writes:  
A modul based on Kalles modul but using the faster block transmission mode can be downloaded at <span class="user"><a href="https://vvvv.org/users/MSBERGER" class="extURL" target="_blank">MSBERGER</a></span>  

<span class="user"><a href="https://vvvv.org/users/r0b" class="extURL" target="_blank">r0b</a></span> writes:  
I'm using the DMX4All USB Device, which can be accessed quite simple in a similar fashion like described above. The driver creates a virtual com-port which then can easily be used.  
---  



# **related vvvvorum discussions**
* using external drivers with vvvv  
  * [about karistouf's littlecat dmxengine](https://vvvv.org/tiki-view_forum_thread.php?topics_offset=1&forumId=18&comments_parentId=23147)  
* DMXinterfaces  
  * [Lanbox](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=20738&forumId=18&highlight=artnet)  
  * [e:cue](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=22792&forumId=18&highlight=artnet)  
* fixtures  
  * ((/tiki-view_forum_thread.php?topics_offset=1&forumId=11&comments_parentId=6712|Where to buy LED-Chains, adressable))