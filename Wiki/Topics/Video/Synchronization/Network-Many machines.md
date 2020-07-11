---
uid: 8bb19977-045e-49b5-82a3-f5a05164e56d
---

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



