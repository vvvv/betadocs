# Writing a DirectShow Video Stream


#### Related nodes
<span class="node">Writer (DShow9)</span>  
<span class="node">VideoIn (DShow9)</span>  
<span class="node">FileStream (DShow9)</span>  



This should work well when connected directly to a <span class="node">VideoIn (DShow9)</span> or <span class="node">FileStream (DShow9)</span> but not so well when connected to an <span class="node">AsVideo (EX9.Texture)</span>.  
In the latter case the rendered image has to be transferred back from the graphiccards memory to cpu memory which is traditionally a slow process.   

<span class="node">Writer (DShow9)</span> writes .avis with a fixed 25 frames per second. For your resulting .avi to be kind of smooth (as smooth as 25fps can be...) you'll therefore have to make sure that your patch is running at exactly 25fps. Use the <span class="node">Timing (Debug)</span> to check this and the <span class="node">MainLoop (VVVV)</span> to limit the framerate. Good luck.  



