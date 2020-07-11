---
uid: 75aad9ef-ba8c-4fa4-a846-03ae5fed5670
---

# General advices
* Make sure videos you want to sync all have equal length and the same codec.   

* Disable features like "CPU SpeedStep" that adapt the speed of the CPU.  The videosync algorithm uses the high resolution performance counter of your cpu to calculate timing. This can become unreliable when the bios changes the cpu speed to save power or performance.   

* Syncing does not seem to work for audio. Needs more investigation...  



# Network/Many machines


#### Related nodes
<span class="node"> FileStream (DShow9 Boygroup)</span>  




**With Boygrouping**  
In a [boygroup](TODO INTERNALLINK:Boygrouping) simply use the <span class="node"> FileStream (DShow9 Boygroup)</span> instead of the usual filestream node and boygroup it. Note: [multi server boygrouping](TODO INTERNALLINK:multiboygrouping) is not supported.  

**Without Boygrouping**  
The <span class="node"> FileStream (DShow9 Boygroup)</span> can also be used in non-boygrouped setups:   
1. on the 'server' machine define the <span class="pin">Port</span>.
1. on every 'client' set the <span class="pin">Is Client</span> (hidden pin) to 1, set the <span class="pin">Port</span> and the <span class="pin">Server IP</span> (hidden pins) of the server. Done.

Examples in your vvvv\girlpower\ directory:  
* Video  

**See also:**  
* <a href="https://vvvv.org/blog/boygroup-time-and-filestream-synchronization" class="extURL blog" target="_blank">Boygroup Time and FileStream Synchronization</a>  





# Locally/Same machine


#### Related nodes
<span class="node"> FileStream (DShow9 Local Master)</span>  
<span class="node"> FileStream (DShow9 Local Slave)</span>  



To sync videos locally (be it in one or multiple instances of vvvv) just place a <span class="node">FileStream (DShow9 Local Master)</span>, define its <span class="pin">Master Port</span> and place as many <span class="node">FileStream (DShow9 Local Slave)</span> as you wish.  

There can only be one master sitting on one particular port. The slaves listening to this master need to have the same 'Master Port' defined.   

If the master node turns red its <span class="pin">Master Port</span> is probably already in use.  

Examples in your vvvv\girlpower\ directory:  
* Video  


