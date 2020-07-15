---
uid: 2eb3d2a2-d4c1-4bc0-bcd8-16e48d756b16
---

# For vvvv.exe


#### /o "path to patch"
#### /r "path to patch"


**/o** opens the patch given by path. This argument followed by a path can be specified any number of times.  

**/r** opens the patch given by path as [root](xref:5eea935d-c82d-4b89-8403-1fbc1d79fb93) patch. This argument can only be specified once, since there can only be one root-patch.  

**Note**   
The path can be relative to vvvv.exe or absolute.   
If there is a space in the path you have to use quotes: /o "my project/patch.v4p"  




#### /allowmultiple


Allows multiple instances of vvvv to run.  




#### /dontregister 


Prohibits registration of addflow, directshowfilter and .v4p filetype.  




#### /shutup


Finishes your project in a clean way: starts vvvv without patch windows. Only renderers are displayed. Only the ALT-F4 shortcut works.  




#### /client ServerIP:PortNr


Start vvvv as boygroup client connecting to the pc specified via [[ServerIP]. Specifying a port is optional. The default (if omitted) is 3333. Note that if you specify a different port here you need to specify the same port via <span class="node">Boygroup (VVVV Server)</span> <span class="pin">Network Port</span>. Also see Boygrouping and [MultiBoygrouping](xref:511c5e9e-a4b0-4f82-914b-2231cea23cfe).  




#### /server


Start vvvv as boygroup server. Also see Boygrouping and [MultiBoygrouping](xref:511c5e9e-a4b0-4f82-914b-2231cea23cfe).  




#### /clockport PortNr


Changes the default port 3334 of the boygroup time synchronization system to the specified port. This can be used to avoid port conflicts with multiple vvvv instance on the same machine.  




#### /dda DeviceID 


Short for "dummy device adapter". Only needed if you're having troubles with a renderer that is supposed to go fullscreen on a monitor other than the primary immediately after starting up a patch.   
Specify as DeviceID the device ID of the monitor a renderer is supposed to go fullscreen on. The device ID can be found by using the graphic-drivers "Identify" option where it prints large numbers on all connected monitors for identifying their order. Take this number minus 1 (i.e. the primary monitor is 0, which you'd never have to specify since this is the default anyway.)  




#### /dx9


Since beta32 vvvv defaults to <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee890072%28v=vs.85%29.aspx" class="extURL" target="_blank">Direct3D 9Ex</a> mode. use this flag to run the legacy dx9 mode, see <a href="https://vvvv.org/blog/cross-process-texture-sharing-depth-rendering" class="extURL blog" target="_blank">cross-process-texture-sharing-depth-rendering</a>  




#### /debug


Starts vvvv in [Debug Mode](xref:36621302-10e7-47fe-a8d0-b609c758974d).  




#### /logstartup


Use this if you have troubles starting vvvv. With this flag vvvv logs all steps it does on startup into a .txt file, placed next to vvvv.exe. You can then post that textfile to the forums bug-section and hope that we can help you identify your problem.  




#### /nodelist "path"


Generates a path/nodelist.xml file for all nodes found beneath the specified path.  




#### /showexceptions true OR false


Enables or disables the exception dialog. By default the exception dialog is disabled in beta releases and enabled in alpha releases.  




#### /artnetsendport PortNr
#### /artnetreceiveport PortNr


To specify a different than the default port (6454) for <span class="node">DMX (Network Artnet Sender)</span> and <span class="node">DMX (Network Artnet Receiver)</span>.  


# For setup.exe



#### /unregister


Same as pressing the "Uninstall" button.  




#### /silent


Just do it, don't show the window.  




#### /log


Use this if you have troubles starting setup. With this flag vvvv logs all steps it does on startup into a .log file, placed next to setup.exe. You can then post that textfile to the forums bug-section and hope that we can help you identify your problem.  


# Using your own Commandline Parameters



Note that you can also specify your very own commandline parameters and read their values from within a patch via the node <span class="node">Args (VVVV)</span>. See its help-patch for further information.  


# Automation



#### args.txt


In vvvvs main program directory, just next to vvvv.exe you can create a file called args.txt. If present this file is parsed and its content is concatenated to the parameters specified via commandline. This is a simple way to specify commandline parameters. A # on the beginning of a line in that file denotes a comment. Comments are not being interpreted by vvvv.   




#### Registry


For what ever reason, you may want to add additional startup options for .v4p-files on rightclicking them in explorer. Open (/o) and Open As Root (/r) are allready there. Search the registry for   
 HKEY_CLASSES_ROOT\VVVV\Shell
and see what you can do.   




#### Batch Files


It may be handy to use different <a href="http://en.wikipedia.org/wiki/.bat" class="extURL" target="_blank">.bat files</a> for calling vvvv.exe with different parameters.   




#### Shortcuts


Make a shortcut to vvvv.exe and rightclick it to edit its properties. There in the *Target* field you can simply add commandline parameters.    


