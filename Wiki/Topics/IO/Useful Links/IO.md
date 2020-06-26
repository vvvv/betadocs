# IO

## Hardware Diagnosis Tools
### General Purpose
### USB
* <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff560019%28v=vs.85%29.aspx" class="extURL" target="_blank">USBview</a> (Universal Serial Bus Viewer, Usbview.exe) is a Windows graphical user interface application that enables you to browse all USB controllers and connected USB devices on your computer. USBView works on all versions of Windows. USBView can enumerate USB host controllers, USB hubs, and attached USB devices. It can also query information about the devices from the registry and through USB requests to the devices. The main USBView window contains two panes. The left pane displays a connection-oriented tree view, enabling you to select any USB device.  


## MIDI
* <a href="http://www.midiox.com/" class="extURL" target="_blank">MIDI-OX</a> is a multi-purpose tool: it is both a diagnostic tool and a System Exclusive librarian. It can perform filtering and mapping of MIDI data streams. It displays incoming MIDI streams, and passes the data to a MIDI output driver or the MIDI Mapper. You can generate MIDI data using the computer keyboard or the built-in control panel.  
* <a href="http://www.bome.com/midi/translator/" class="extURL" target="_blank">Bome's Midi Translator</a> lets you translate MIDI messages (e.g. from a keyboard or a control surface) to different MIDI messages, or to emulated keystrokes for controlling other programs.  
* <a href="http://www.nicolasfournel.com/" class="extURL" target="_blank"> some amazing midi tools</a>  

## MIDI Loopback Devices
virtual midi ports/cables, to connect different software via midi:  
* <a href="http://www.maplemidi.com/Maple_driver.html" class="extURL" target="_blank">Maple Virtual Midi Cable</a>  
* <a href="http://www.midiox.com/myoke.htm" class="extURL" target="_blank">MIDI Yoke Junction</a>  
* <a href="http://www.nerds.de/en/loopbe1.html" class="extURL" target="_blank">LoopBe1</a>  

## Lighting Tools
* <a href="http://www.le-chat-noir-numerique.fr/index_eng.html" class="extURL" target="_blank"> WhiteCat </a> a free open source lighting board enabling to work with DMX devices, midi devices. Cues, performance structure, ArtNet IN and OUT ( remoting VVVV is very easy using WhiteCat Cuelist and recording habilities, or getting data in Artnet from VVVV). WhiteCat is dedicated to traditionnal lights (dimmers). Coded in C-C++, searching for new coders :)  
* <a href="http://karistouf.free.fr/developpement%20logiciel.html" class="extURL" target="_blank"> Schwartzpeter</a> is a free lighting desk, ancestor of WhiteCat. It is remotable in midi (hardware and udp). Cues, patch, dimmer laws, chasers, midi receiving / sending, ascii import/export.  
* <a href="http://moicestpilou.free.fr/" class="extURL" target="_blank">free ascii transcoding tool</a>  
* <a href="http://www.chamsys.co.uk/magicq" class="extURL" target="_blank">MagicQ</a> Pc lighting software fully featured pc editor for their consoles. Supports Entec, pepperoni, artnet outputs, 16 universes, cues stacks, media server support.  

## Networking
* <a href="http://www.tightvnc.org" class="extURL" target="_blank">TightVNC</a> is better than RealVNC, because it allows multiple clients to connect simultaneously.  
* <a href="http://www.inputdirector.com/" class="extURL" target="_blank">Input Director</a> is a Windows application that lets you control multiple Windows systems using the keyboard/mouse attached to one computer. You can  
  * share a single keyboard/mouse across a set of systems. You switch which system receives the input by moving the cursor.  
  * Input Director also supports a "shared" clipboard, in which you can copy data onto the clipboard on one system, transition across to another and paste.  
  * since vvvv_beta20 you even can **copy a selection of nodes** on one PC **and paste** them into a patch **on a second PC**.  
  * you even can use a whole KVM-cluster of PCs (each running ID as Master) and your laptop besides as ID-slave. **no matter which PC is selected by KVM** you can **sweep over to your laptop and back**. Input Director is definetely very addictive and always will be free for personal non-commercial use.  

* <a href="http://synergy2.sourceforge.net" class="extURL" target="_blank">Synergy</a> allows you to use your main mouse and keyboard to control other computers. You can configure the topology, eg, "I have another computer to the right of my main one" and control is transferred seamlessly when your mouse moves off the righthand side of the screen. Works reliably, it's free and will help prevent RSI!  
* <a href="http://beyondcopy.sourceforge.net/" class="extURL" target="_blank">BeyondCopy</a> is a LAN hosts clipboard synchronism tool. BeyondCopy allows you to copy something in one computer, and paste it in another computer directly. It is useful if you have to work using two or more computers at the same time. File Copying feature works under Windows 2000/XP/2003. It is an open source software under GNU General Public License 3.0.  
* <a href="http://www.netsetman.com/" class="extURL" target="_blank">NetSetMan</a>  is a network settings manager which can easily switch between 6 different, visually structured profiles including: IP Address, Subnet Mask, Default Gateway, DNS Server, Computer Name, Workgroup, DNS Domain, WINS Server, Default Printer,  Network Drives, Run Scripts. a "must have" for laptops.  
* <a href="http://technet.microsoft.com/en-us/sysinternals/bb896644.aspx" class="extURL" target="_blank">PortMon</a> is a utility that monitors and displays all serial and parallel port activity on a system. It has advanced filtering and search capabilities that make it a powerful tool for exploring the way Windows works, seeing how applications use ports, or tracking down problems in system or application configurations. Debug output from any computer accessible via TCP/IP - even across the Internet. You can monitor multiple remote computers simultaneously. Portmon will even install its client software itself if you are running it on a Windows NT/2K system and are capturing from another Windows NT/2K system in the same Network Neighborhood.  
* <a href="http://home.cs.tum.edu/~jain/software.php#Mirror" class="extURL" target="_blank">Mirror</a>, a commandline tool of Dominik Jain, makes exact copies of directories (or entire directory structures). It will overwrite existing files only if necessary and delete files in the destination that are no longer present in the source (unidirectional synchronization). Mirror can ignore files that match regular expressions or file masks. <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span> integrating this tool into vvvv.  
* <a href="http://technet.microsoft.com/en-us/sysinternals/bb896649.aspx" class="extURL" target="_blank">PsTools</a> is a simple and light network management process.Usefull for boygroup. Allow kills,starts, copy... from one computer to other computers over networks.  

## Graphiccards Tools/Drivers
* <a href="http://www.laptopvideo2go.com/" class="extURL" target="_blank">laptopvideo2go</a> allows you to install the newest nvidia-drivers on any laptop with nvidia graphiccard  
* <a href="http://www.entechtaiwan.com/util/ps.shtm" class="extURL" target="_blank">Powerstrip</a> allows you to precisely set a graphiccards refresh frequency independent of the driver  

## EventGhost
* <a href="http://www.eventghost.de/" class="extURL" target="_blank">EventGhost</a> is an open-source automation tool for MS Windows, that can be extended through plugins. It can use different input devices like infrared or wireless remotes to trigger macros, that on their part control a computer and its attached hardware. After the user has configured everything to its needs, the program will run silently in the system tray and waits for an event to arrive. So it can be used to control a Media-PC with a normal consumer remote for example.  

## Programmable Input Emulator
* <a href="http://glovepie.org/glovepie.php" class="extURL" target="_blank">GlovePIE</a> allows to connect several things to vvvv via MIDI or OSC  
  * P5 DataGlove  
  * Microsofts Speech Recognition  
  * Text to Speech  
  * ForceFeedback  
  * Multiple Mice  
  * Nintendo Wii  
* <a href="http://www.autohotkey.com/" class="extURL" target="_blank">AutoHotkey</a> is a free, open-source utility for Windows.  
  * Automate almost anything by sending keystrokes and mouse clicks.  
  * You can write a mouse or keyboard macro by hand or use the macro recorder.  
  * Create hotkeys for keyboard, joystick, and mouse. Virtually any key, button, or combination can become a hotkey.  