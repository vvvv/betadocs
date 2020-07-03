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
Only [primitive data](TODO INTERNALLINK:patching-basics#data-types) (values, strings, colors, enums) is being taken care of automatically. Therefore all resources the server patch accesses have to be available on the clients file system as well. Synchronizing the directory structure of a server with multiple clients can easily be achieved with additional tools. Have a look at [RemoterSA](TODO INTERNALLINK:RemoterSA) or <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span>.  


