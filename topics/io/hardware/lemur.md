---
uid: de35f61c-57e7-481e-8542-37d0c820e844
---

# Lemur
*The Lemur device from <a href="http://www.jazzmutant.com/" class="extURL" target="_blank">jazzmutant</a> is a tangible multitouch interface, that allows you to create your own interface and send your data via midi or osc.*  

![](~/img/if.jpg "")![](~/img/touch.jpg "")  

This short Tutorial will show you how to connect your Lemur device to VVVV via the <a href="http://cnmat.berkeley.edu/OpenSoundControl/" class="extURL" target="_blank">osc</a> protocol.  


![](~/img/ip.jpg "")  

fisrt step is to set up an ip adress for your lemur device (settings->ip settings). then you have to create your personal interface within the lemur editor.  


![](~/img/osc_message.jpg "")  

next step is to select a controller and set up a name for the osc message. the shown name for the message is "/room". don´t forget the slash in front of the messagename!  


![](~/img/osc.jpg "")  

it´s important to set up every network client with a specific ip adress inside the lemur osc settings. otherwise it wouldn´t work. thats all on the lemur side. next step is to open VVVV.  


![](~/img/patch.jpg "")  

as you can see, only a few nodes are needed to get the controller values from the leumr device. just create an udp(server) and an osc decoder to get the message strings from the network. use the same settings for the messagename (Slash!) and the port (avoid port 8001 and 8002 used by the jazz editor software otherwise your patch won't work when the jazz editor is connected to the lemur (green arrow)). as on the lemur device (check that your firewall don´t block it).  
 
That´s it. Now have a lot of fun with the lemur and of course with VVVV.  