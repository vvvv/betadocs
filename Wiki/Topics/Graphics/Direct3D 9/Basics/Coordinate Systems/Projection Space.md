# Projection Space


And this is what the camera sees:  
![](~/img/CameraImage4.png "")  



Projection space (aka Screen space, Clip space, Image space) finally is the 2d space of the screen. To project a Mesh onto the screen its vertex positions (in View space) are multiplied by the ProjectionMatrix. The ProjectionMatrix is specified via the <span class="pin">Projection Transform</span> on the <span class="node">Renderer (EX9)</span>.  




