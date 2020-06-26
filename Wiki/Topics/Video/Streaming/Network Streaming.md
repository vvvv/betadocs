# Network Streaming

#### Related nodes
<span class="node">MJpegStream (EX9.Texture Sender)</span>  
<span class="node">MJpegStream (EX9.Texture Receiver)</span>  

<span class="node">AsRaw (EX9.Texture)</span>  
<span class="node">DynamicTexture (EX9.Texture Raw)</span>  



A texture can be sent over the network using either the MJpegStream nodes or [Spout](TODO INTERNALLINK:software#spout) in connection with <a href="http://techlife.sg/TCPSpout/" class="extURL" target="_blank">TCPSpout</a>.  

Alternatively you can convert a texture to a byte-spread using AsRaw (EX9.Texture) and send it over the network, eg. via [TCP](TODO INTERNALLINK:protocols#udp-tcp) and convert the byte-spread back to a texture using DynamicTexture (EX9.Texture Raw).  



