---
uid: 2da366b8-602a-41dd-baf5-7e99a3e487e6
---

# Network Streaming

#### Related nodes
<span class="node">MJpegStream (EX9.Texture Sender)</span>  
<span class="node">MJpegStream (EX9.Texture Receiver)</span>  

<span class="node">AsRaw (EX9.Texture)</span>  
<span class="node">DynamicTexture (EX9.Texture Raw)</span>  



A texture can be sent over the network using either the MJpegStream nodes or [Spout](xref:f10200c2-93fb-4a66-886c-26b8d7a20e6a) in connection with <a href="http://techlife.sg/TCPSpout/" class="extURL" target="_blank">TCPSpout</a>.  

Alternatively you can convert a texture to a byte-spread using AsRaw (EX9.Texture) and send it over the network, eg. via [UDP or TCP](xref:f77e634d-00d7-4cb1-b9d4-69573c6b9bcd) and convert the byte-spread back to a texture using DynamicTexture (EX9.Texture Raw).  



