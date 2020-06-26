# Antialiasing


<a href="http://mathworld.wolfram.com/Antialiasing.html" class="extURL" target="_blank">Antialiasing at Mathworld</a>  
<a href="http://en.wikipedia.org/wiki/Multisample_anti-aliasing" class="extURL" target="_blank">Antialiasing at Wikipedia</a>  

![](~/img/Basics-Antialiasing.png "")  



Rotated or curved objects always look jagged if Antialiasing is turned off (which is the default). That's because pixels are squares and there are (still) not so many of them to represent curves or diagonals in a way that the eye will not notice squares.   

Use the 'Fullscreen / Windowed Antialiasing Quality' settings of the <span class="node">Renderer (DX9)</span> to specify the desired quality. Usually a value of 4 is a good choice.  

This setting is available via [Inspektor](TODO INTERNALLINK:the-gui#herr-inspektor).   

