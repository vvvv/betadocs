---
uid: 71ad560c-5f5e-4f02-9573-22583a992ac4
---

# RemoterSA
Remoter is typically useful for boygrouping scenarios where a bunch of clients are being treated from a server. It is basically <a href="http://pstoolsgui.sourceforge.net/" class="extURL" target="_blank">just</a> <a href="http://www.davitools.com/fepstools/fepstools.aspx" class="extURL" target="_blank">another</a> GUI for <a href="http://technet.microsoft.com/de-de/sysinternals/bb896649.aspx" class="extURL" target="_blank">PsTools</a> optimized for the needs in large client/server installations.  

A simple standalone GUI lets you specify a list of clients that are to be controlled. You can WakeOnLAN/Reboot/Shutdown clients and  start/restart/stop processes on them. Also basic WatchDog functionality is implemented that watches processes on remote clients and restarts them or the whole client in case the process cannot be found.  

![](~/img/remotersa_beta5.png "")  

## Download
get the latest version of RemoterSA from its contribution page: <a href="https://vvvv.org/contribution/RemoterSA" class="extURL contribution" target="_blank">RemoterSA</a>  
plus get the following:  
* <a href="http://technet.microsoft.com/de-de/sysinternals/bb896649.aspx" class="extURL" target="_blank">PsTools</a>  
* <a href="http://www.uvnc.com/download/" class="extURL" target="_blank">UltraVNC</a>  

## Install
Remoter and the PsTools don't need to be installed, just put them in a nice place on your harddisk. UltraVNC comes with its own installer.   

# Settings
## PsTools
Here you specify the path where Remoter finds the PsTools and Username/Password for an admin account on the systems to remote. Note that all clients you wish to remote need that same Username/Password account. **An empty password is not allowed!**  

With the little plus button to the left you can add a remote process that will then be available for selection in the comboboxes on the *Commands* tab. Specify a remote process with its full path in the first edit field. **This exact path needs to exist on the PC that runs RemoterSA!** Commandline arguments to start this process go in the second edit field.   

>note:  
Getting PsTools to work can be a bit tricky. The following seem to be the most important settings to check:  
* Turn on File and Printer sharing  
* If executing commands remotely works, but is very slow (it should be instant!), try with all firewalls disabled  
* If it doesn't work, you need to enable access to the Admin shares. Via regedit, set: HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\system\LocalAccountTokenFilterPolicy to 1 (DWORD32).  
* If the *Watch* feature of the *Tasks* doesn't seem to work, it is likely that you have to <a href="https://kb.paessler.com/en/topic/15543-how-do-i-enable-the-remote-registry-service-on-a-windows-pc" class="extURL" target="_blank">enable the Remote Registry Service</a>  
  

## VNC
Here you specify the path to where you installed UltraVNC. Note that you need to install a vnc-server on all the clients you wish to vnc to. And set them all the same vnc-password.  

## Mirror
In the *Source Path* you specify your projects root path, like:  
 C:\MYPROJECT

The *Target Path* must be a directory that is shared on the clients. Specify it without the clients name or ip-address, just like:  
 \myproject

The *Ignore Pattern* has to be filled with entries separated by semicolon. You can specify filemasks as well as directory names, like  
 \*~.xml; *\.git

# IPs
Add IPs to the list by entering them in the box and pressing ENTER or the **+** button. You can also enter a range of IPs by typing something like:   
 192.168.0.10-25

Remove IPs from the list by pressing their **X** button. Pressing the **VNC** button opens a VNC viewer to that client, pressing the **EXP** button explores the clients *Target Path* as specified in the mirror-settings.  

Select an IP with a left-click, deselect it with a right-click. Note that you can also select/deselect multiple IPs using click-drag.  

The first color-field indicates whether the IP can be pinged. The second one indicates whether a watched process (via a Task, see below) is running or not.  

# Groups
Allows you to define (even overlapping) groups/selections of IPs to select/deselect at once and to operate Tasks on (see below). Enter a group name and press enter or the **+** button. Then click on the groups **E** button to edit its name and IPs.   

Add a single IP or a range of IPs (as mentioned above) per line, then press the groups **S** button to save the changes.  

Select a group with a left-click, deselect it with a right-click. Note that you can also select/deselect multiple groups using click-drag.  

The first color-field indicates whether all of the groups IPs can be pinged. The second one indicates whether a watched process (via a Task, see below) is running or not.  

# Commands
All commands are always executed on all selected IPs.  

## Start/Stop processes
The first section features 3 buttons to start, restart and kill processes. Select one of the processes you have configured in the *Settings* tab from the combobox. Now you can start, restart or kill that process on all selected IPs.   

## Start/Stop PCs
The next section lets you start, reboot and shutdown PCs. **WakeOnLan** only works for PCs that have a MAC address associated to their IP. (To retrieve a PCs MAC addresses press **Get a MAC + Hostname** while the PC is running - this may take a while!). Note that for this operation the Username/Password as specified under Settings\PsTools are used where a non-empty password is mandatory.  

## Mirror
The **Mirror Now** button does just that. Using your specified source-, targetpath and ignore pattern as commandline arguments it mirrors the specified directories. With the *Test Only* checkbox checked you can see (in the console) what the mirror would do, without actually changing anything.  

## Task
Last is the Task section. Enter task description in the EditBox and klick *Add Task*. Then clicking on the *E* button (rightmost) you can edit the task. First is the description, followed by a group (to operate on) and a process. The *Timout* specifies the number of seconds before an attempt to start a remote process is canceled, if the remote PC cannot be reached.  
If you check the *Watch* checkbox you can also specify what is supposed to happen, if the process cannot be found remotely: do nothing, restart the process, or reboot the PC.   

>note:  
On remote PCs this can only detect processes that completely vanished. Hanging processes will not be detected! In order for processes to better vanish on fail make sure to disable windows error reporting:  
 My Computer->Properties->Advanced->Error Reporting->Disable (no notify!)

For local processes Remoter can also detect if they are hanging and restart them or reboot accordingly. Still it is reccommended to turn of error reporting as mentioned above.  
  


# Simulator
This is for the common case to simulate a thirdparty mediacontrol software that typically sends simple strings via udp/tcp to control a boygroup.   

Set your target PCs IP and port and press the *Connect* button. Then add simple strings to the list by entering them in the upper edit-field and pressing *ENTER* or the plus sign.   

Left-click a string to send the command. Right-click a selected command to remove it from the list.  

# Source
https://github.com/vvvv/RemoterSA  

# Change Log
##  beta8 29 10 2018
* can now run remote processes as admin  

##  beta7 16 10 18
* includes free <a href="http://utilfr42.free.fr/util/Mirror.php?sLang=en" class="extURL" target="_blank">mirror</a> tool by Guillaume Ryder  
* fixes issue with saving   
* fixes issue with process dropdown not updating when new process was added  
* added some explanatory tooltips  
* mirror excludes for directories now have to be specified differently, see tooltip  

##  beta6 31 03 11
* small fix for windows 7  

##  beta5 08 12 09
* GUI overhaul  
* added the concept of tasks  
* can now also display hostname of clients  
* IPs are now always sorted from lowest to highest  
* added button to start VNC viewer on IP that is not added to the list  
* added new default groups: show all offline/online IPs  
* fixed problem with adding a new group  

## beta4 10 09 09
* multiple remote(watch) processes can now be preconfigured with commandline arguments in the settings tab  
* paths with spaces are now handled correctly  
* new mirror "test only" option  
* mirror returns full loginfo  

## beta3 26 08 09
* now pings and watches remote processes in a separate thread  
* added GUI to deal with groups of IPs (for very large boygroups)  

## beta2 10 04 09
* debugged in a realworld boygroup  
* added basic MediaControl Simulator (TCP only)  

## beta1 - 22 03 09 - initial release