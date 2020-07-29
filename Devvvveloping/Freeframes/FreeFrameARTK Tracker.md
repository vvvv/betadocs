---
uid: 82e19d60-1c44-46ba-bb39-d79e38ca4bbb
---

# FreeFrameARTK Tracker

## short description
implemenation of the ARToolkitPlus library for tracking of AR markers. returns transformation of multiple markers in space.  
## licence
**GNU General Public License (GPL)**  
<a href="http://www.gnu.org/licenses/gpl.html" class="extURL" target="_blank">english</a>  
<a href="http://www.gnu.de/documents/gpl.de.html" class="extURL" target="_blank">german</a>  
## authors
<span class="user"><a href="https://vvvv.org/users/joreg" class="extURL" target="_blank">joreg</a></span>  
<span class="user"><a href="https://vvvv.org/users/sonderformat" class="extURL" target="_blank">sonderformat</a></span>  



## download source
get the latest source from the subversion repository:  
 https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/addonpack/src/nodes/freeframes/ARTK+Tracker

## dependencies
<a href="http://studierstube.icg.tu-graz.ac.at/handheld_ar/artoolkitplus.php" class="extURL" target="_blank">ARToolkitPlus library</a>  

## project language/ide
c++/<a href="http://www.codeblocks.org" class="extURL" target="_blank">CodeBlocks</a>  



## usage info
the ARTK+Tracker.dll is opensource licensed under the GPL (see above) because it is based on other GPLed code. vvvv is closed source software which means (as i understand the issue) that it must not access any GPL code.  

while it is therefor definitely illegal to use ARTK+Tracker.dll with vvvv for commercial interrests i am not sure about educational and research purposes.  

until anybody offers us a more detailed understanding of the situation everybody be his own judge.  

supports 8-bit greyscale images & 16-bit RGB565 images.  

## FAQ
### the provided help file doesn't show anything in the renderer?
for the patch to show an image you have to specify a Camera File. while it is [rather](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=25101&forumId=7&highlight=artk+) difficult (but posssible)] to generate a specific camera file for your camera there is a generic one, that comes with the artoolkitplus download from:  
<a href="http://studierstube.icg.tu-graz.ac.at/handheld_ar/artoolkitplus.php" class="extURL" target="_blank">http://studierstube.icg.tu-graz.ac.at/handheld_ar/artoolkitplus.php</a>  
direkt link to download is:  
<a href="http://studierstube.icg.tu-graz.ac.at/handheld_ar/download/ARToolKitPlus_2.1.1.zip" class="extURL" target="_blank">http://studierstube.icg.tu-graz.ac.at/handheld_ar/download/ARToolKitPlus_2.1.1.zip</a>  
there you find the file LogitechPro4000.dat in the  
 sample\simple\data directory. 

### what are the .pat files?
with .pat files you could specify custom patterns, but their use is not yet implemented. the .pat pin on the node is not of any use right now. therefore you can only use the default built in patterns you can also find in the download above.