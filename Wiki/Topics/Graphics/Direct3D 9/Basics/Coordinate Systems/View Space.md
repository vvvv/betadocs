# View Space


![](~/img/ViewSpace2.png "")  


View space (aka camera space) is the coordinate system relative to the camera. To place a Mesh into View space its vertex positions (in World space) are multiplied by the ViewMatrix. The ViewMatrix is specified via the <span class="pin">View</span> on the <span class="node">Renderer (EX9)</span>. It defines position and rotation of the camera.  



