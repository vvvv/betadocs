---
uid: 654fb0a1-2f52-4425-8ab7-2f82d4785d54
---

# Problems




**vvvv takes ages to open**  

As <span class="user"><a href="https://vvvv.org/users/antokhio" class="extURL" target="_blank">antokhio</a></span> reported in <a href="https://discourse.vvvv.org/t/dx11-pack-stops-beta5-from-starting-up/14718/10" class="extURL" target="_blank">this thread</a> there seems to be an issue with Windows Defender causing those delays on some PCs. Go to *Windows Defender > Settings > Exceptions* and add your vvvv directory as an exception.   




**A virus scanner says that vvvv is a virus. Is that so?**  


Almost certainly not! Most likely your scanner complains about WinLockDLL.dll which is used by <span class="node">Styx (Windows)</span>.   




**Error Message: "The application failed to initialize because d3dx9_30.dll is missing. Reinstalling the software might solve the problem"**  


Sorry for that ugly error-message.   
Please run setup.exe where you should be notified of a missing DirectX9 installation. Best download and run the WebInstaller which should solve the problem.   
>note:  
Even if you have DirectX 10/11 (on Vista/Windows7) you'll have to install DirectX9.  




**vvvv shows up in the task bar, there may be a DirectX Renderer, but there is no patch window**  


* Have you run setup.exe at least once as Administrator? Even if you are admin try to rightclick setup.exe and "Run as Administrator".  

* Are you using Windows 7 and running VVVV out of the c:\Program Files folder? There might be a user rights issue with registering Plugins (at least in Beta 24.1) - try putting your VVVV folder at an *unprotected*location like your desktop and try running as administrator again.  




**The Renderer's Window is gray**  


This is almost certainly a graphic driver problem. Make sure you have its latest version installed or even cosider a graphic card upgrade if the problem persists.  




**Cannot start VVVV: OMP abort**  


Read [this thread](https://vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=23077#threadId28724).  




**My patch has some bugs and/or Red Nodes**  


Read [Debugging](TODO INTERNALLINK:Debugging).  




**I have dropped frames when writing to external USB drive**  


Try disabling "USB selective Suspend " in advanced power settings in Control Panel -> Power Options -> Change plan settings -> Change advanced power settings -> USB settings  


# Helpful Methods



**/logstartup**  


Start vvvv with the [Commandline Argument](TODO INTERNALLINK:Commandline Parameters) **/logstartup**.  

Use this if you have troubles starting vvvv. With this flag vvvv logs all steps it does on startup into a .txt file, placed next to vvvv.exe. You can then post that textfile to the forum and we'll see what we can do.  




**Renderer (TTY)**  


Always use a <span class="node">Renderer (TTY)</span>. This is also vvvvs error console so it may provide some information you could post in the forums.  




**Config.exe**  
![](~/img/vvvv_Config.png "")   



Use **Config.exe** for:  
--- checking whether all dependencies are properly installed (all boxes are green)  
--- setting FileType Associations (.v4p, .vl) and some other parameters.  

Running config.exe will ask you for administrative rights which you'll have to accept. If it doesn't ask you, you'll have to run config.exe as administrator manually by rightclicking on it and selecting "Run as..."  

