---
uid: b99ee79d-7cbd-4dc5-94ab-94927b18dcd0
---

# Directory Structure

![](~/img/Boygrouping-ProjectFolder.png "")   




It is generally good practice to create a directory structure like the following when working on a specific project with vvvv.   

In a boygroup-setup specifically it is necessary to **create an identical directory structure on the server and all clients**.   

>C:\MYPROJECT\patches  
C:\MYPROJECT\resources  
C:\MYPROJECT\vvvv  

**The clients won't need the .v4p files in the \patches directory.**  
They will receive all their nodes magically from the server! Still you may want to place .fx or .dll files in this directory on the clients, if they are also there on the server. Also it is no problem if the clients also get all the .v4p files mirrored as long as you understand that they will not be used.  

**Boygrouping doesn't transmit any resources (textures, videos, effect files, ..) over the network.**   
Only [node-connection](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#data-types) (values, strings, colors, enums) is being taken care of automatically. Therefore all resources the server patch accesses have to be available on the clients file system as well. Synchronizing the directory structure of a server with multiple clients can easily be achieved with additional tools. Have a look at [RemoterSA](xref:71ad560c-5f5e-4f02-9573-22583a992ac4) or <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span>.  


