# Preparations on the Clients

![](~/img/Boygrouping-ClientWindow.png "")   




The client side of patching is rather transparent. Actually **no patching needs to be done at all on the clients**.   

All you have to do is to start vvvv.exe with the following [commandline parameter](TODO INTERNALLINK:Commandline Parameters):  

 vvvv.exe /client *ServerIP*

Example:  

 vvvv.exe /client 192.168.0.100

Assuming that 192.168.0.100 is the ip-address of your server. You'll see that vvvv is indeed in client-mode as it pops up a default patch with the title **//CLIENT of 192.168.0.100**  

Note that the patch is [locked](TODO INTERNALLINK:patching-basics#locking-a-patch) by default.  


