---
uid: ac57e3df-29a2-4f3b-a98a-3c0057a3308c
---

# Preparations on the Clients

![](~/img/Boygrouping-ClientWindow.png "")   




The client side of patching is rather transparent. Actually **no patching needs to be done at all on the clients**.   

All you have to do is to start vvvv.exe with the following [Commandline Parameters](xref:2eb3d2a2-d4c1-4bc0-bcd8-16e48d756b16):  

 vvvv.exe /client *ServerIP*

Example:  

 vvvv.exe /client 192.168.0.100

Assuming that 192.168.0.100 is the ip-address of your server. You'll see that vvvv is indeed in client-mode as it pops up a default patch with the title **//CLIENT of 192.168.0.100**  

Note that the patch is [locked](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#locking-a-patch) by default.  


