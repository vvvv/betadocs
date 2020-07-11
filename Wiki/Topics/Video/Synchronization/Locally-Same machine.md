---
uid: 41d92986-4268-4989-9557-1449d40e726e
---

# Locally/Same machine


#### Related nodes
<span class="node"> FileStream (DShow9 Local Master)</span>  
<span class="node"> FileStream (DShow9 Local Slave)</span>  



To sync videos locally (be it in one or multiple instances of vvvv) just place a <span class="node">FileStream (DShow9 Local Master)</span>, define its <span class="pin">Master Port</span> and place as many <span class="node">FileStream (DShow9 Local Slave)</span> as you wish.  

There can only be one master sitting on one particular port. The slaves listening to this master need to have the same 'Master Port' defined.   

If the master node turns red its <span class="pin">Master Port</span> is probably already in use.  

Examples in your vvvv\girlpower\ directory:  
* Video  

