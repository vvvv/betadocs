# Texture Writer


#### Related nodes
<span class="node">Writer (EX9.Texture)</span>  
<span class="node">Writer (EX9.Texture NRT)</span>  
<span class="node">Writer (EX9.Texture AVI)</span>  



* The <span class="node">Writer (EX9.Texture)</span> lets you save textures to files of different graphic formats. Best used in connection with <span class="node">DX9Texture (EX9.Texture)</span> which converts the output of a Renderer (EX9) node to a texture.   

* For high resolution output try the non-realtime renderer <span class="node">Writer (EX9.Texture NRT)</span> which renders a still image sequence of any resolution your graphic card supports (typically up to 4096x4096 or 8192x8192). Use <a href="http://www.virtualdub.org/" class="extURL" target="_blank">VirtualDub</a> or another video software to convert the images into your favourite movie format. Best quality, but non-realtime, meaning this is not suitable if you want to record animations with live-interaction.   

* Quite similar to the previous node, but <span class="node">Writer (EX9.Texture AVI)</span> saves the uncompressed .avi files with a given framerate. Make sure to use it similarly to the Writer (EX9.Texture NRT) module with a MainLoop (VVVV) node with "Time Mode" set to 'Increment'.  



