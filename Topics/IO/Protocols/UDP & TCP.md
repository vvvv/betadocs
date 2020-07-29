---
uid: f77e634d-00d7-4cb1-b9d4-69573c6b9bcd
---

# UDP & TCP


<a href="http://en.wikipedia.org/wiki/User_Datagram_Protocol" class="extURL" target="_blank">UDP</a>  
<a href="http://en.wikipedia.org/wiki/Transmission_Control_Protocol" class="extURL" target="_blank">TCP</a>  

#### Related nodes

<span class="node">UDP (Network Client)</span>  
<span class="node">UDP (Network Server)</span>  
<span class="node">TCP (Network Client)</span>  
<span class="node">TCP (Network Server)</span>  

<span class="node">Tokenizer (Raw FixedLength)</span>  
<span class="node">Tokenizer (Raw LengthPrefix)</span>  
<span class="node">Tokenizer (Raw Postfix)</span>  
<span class="node">Tokenizer (Raw Frame)</span>  

<span class="node">PrefixLength (Raw)</span>  
<span class="node">PostfixBytes (Raw)</span>  
<span class="node">FrameBytes (Raw)</span>  


The main difference between the UDP and TCP protocols is the fact that while UDP transmits faster, it does not guarantee all data to arrive. TCP tends to be a bit slower but it does guarantee the arrival of all data sent. Therefore UDP is generally used for streams of data where it does not matter if a single data is missing whereas TCP is used when every single data sent needs to arrive on the other side. Also UDP allows you to send broadcasts to a range of listeners. This can easily be done by using a broadcast IP like x.y.z.255 (where x.y.z is your subnet, like e.g. 192.168.0) for the <span class="pin">Remote Host</span>.  

Note that choosing TCP requires you to take care of <a href="http://blog.stephencleary.com/2009/04/message-framing.html" class="extURL" target="_blank">message framing</a> for which vvvv offers the Tokenizer nodes.   

More infos in your vvvv\girlpower\ directory:  
* IO\Networking  



