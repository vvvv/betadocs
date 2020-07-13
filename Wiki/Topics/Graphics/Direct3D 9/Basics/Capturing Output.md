---
uid: 9a69e819-8ea6-4c5d-807e-b283863abc4c
---

# Still Screenshots




**Ctrl+1** / **Ctrl+2**  
Screenshot of the active vvvv-window with / without the window border.  

**Shift+Ctrl+1** / **Shift+Ctrl+2**  
The same as above, but the file-save dialog is invoked.  

**Ctrl+3**  
Make a screenshot name it and post directly to the "Screenshots of the Days" on vvvv.org (as seen on the front page).  

* If you shoot a patch, the file is placed in the patchs directory. Press ALT+E to open an explorer window to this path.   
* If you shoot any other vvvv-window the file is placed in the directory in which its parent patch is placed in (e.g. shoot a renderer and search the image in the directory of the patch in which the Renderer node is placed in).  
* If a patch is not yet saved (shows something like 0.v4p//// in its windowtitle) you'll find the the .png in vvvvs root directory.  
* Pressing one of the shortcuts also copies the image to the clipboard which allows you to paste (Ctrl+V) it into other programs like Photoshop, Word etc.  





# Screen Recorder


#### Related nodes
<span class="node">Rekorder (Windows)</span>  
<span class="node">ScreenShot (EX9.Texture)</span>  
<span class="node">Writer (EX9.Texture)</span>  



* Use <span class="node">Rekorder (Windows)</span> to capture ANY window into an animated GIF. The <span class="pin">Progress</span> output helps to create seamless animated loops. Use **Ctrl+4** to capture an active window.   

* There are also several screen capture tools listed on the [video software links](TODO INTERNALLINK:video software links) page that can record portions of the screen to a movie file.   

* Alternatively you can also use <span class="node">ScreenShot (EX9.Texture)</span> in connection with a <span class="node">Writer (EX9.Texture)</span> and patch your own screen recorder.   






# Capture DirectX Backbuffer


#### Special tools:
<a href="http://www.fraps.com/" class="extURL" target="_blank">Fraps</a>  
<a href="http://www.exkode.com/home-en.html" class="extURL" target="_blank">Dxtory</a>  
<a href="http://obsproject.com/" class="extURL" target="_blank">Open Broadcaster Software (OBS)</a>  



These tools directly capture the backbuffer of any directx application. On their website they claim to record at high framerates and high resolution directly to .avi files.  

There's also the promising nvidia shadowplay software (no vvvv support yet).  





# Texture Writer


#### Related nodes
<span class="node">Writer (EX9.Texture)</span>  
<span class="node">Writer (EX9.Texture NRT)</span>  
<span class="node">Writer (EX9.Texture AVI)</span>  



* The <span class="node">Writer (EX9.Texture)</span> lets you save textures to files of different graphic formats. Best used in connection with <span class="node">DX9Texture (EX9.Texture)</span> which converts the output of a Renderer (EX9) node to a texture.   

* For high resolution output try the non-realtime renderer <span class="node">Writer (EX9.Texture NRT)</span> which renders a still image sequence of any resolution your graphic card supports (typically up to 4096x4096 or 8192x8192). Use <a href="http://www.virtualdub.org/" class="extURL" target="_blank">VirtualDub</a> or another video software to convert the images into your favourite movie format. Best quality, but non-realtime, meaning this is not suitable if you want to record animations with live-interaction.   

* Quite similar to the previous node, but <span class="node">Writer (EX9.Texture AVI)</span> saves the uncompressed .avi files with a given framerate. Make sure to use it similarly to the Writer (EX9.Texture NRT) module with a MainLoop (VVVV) node with "Time Mode" set to 'Increment'.  





# Writing a DirectShow Video Stream


#### Related nodes
<span class="node">Writer (DShow9)</span>  
<span class="node">VideoIn (DShow9)</span>  
<span class="node">FileStream (DShow9)</span>  



This should work well when connected directly to a <span class="node">VideoIn (DShow9)</span> or <span class="node">FileStream (DShow9)</span> but not so well when connected to an <span class="node">AsVideo (EX9.Texture)</span>.  
In the latter case the rendered image has to be transferred back from the graphiccards memory to cpu memory which is traditionally a slow process.   

<span class="node">Writer (DShow9)</span> writes .avis with a fixed 25 frames per second. For your resulting .avi to be kind of smooth (as smooth as 25fps can be...) you'll therefore have to make sure that your patch is running at exactly 25fps. Use the <span class="node">Timing (Debug)</span> to check this and the <span class="node">MainLoop (VVVV)</span> to limit the framerate. Good luck.  





# Record Monitor Output




Simply connect a video recording device to the video output of your graphics card. Then switch to fullscreen and press record.   

This method has the very advantage, that you don't need additional pc performance.  

