---
uid: 3da47c95-1873-4846-81f6-3617982efc11
---

# Fullscreen on Clients

![](~/img/boygroupfullscreen.jpg "")  


The standard boygrouping scenario is that you still want to be patching on the server while your clients already are in fullscreen.   

Therefore you'll want the Renderers <span class="pin">Fullscreen</span> be set to 1 on the clients but 0 on the server.   

Remember that the only way to distinguish the server from all the clients (and the clients from each other) is the ClientID. Depending on this value you can set a renderer on the server in windowed mode while it is fullscreen on all clients.   


