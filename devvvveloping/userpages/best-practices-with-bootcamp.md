---
uid: be87c353-6012-4044-8a1e-5ed0afb1c799
---

# Best practices with Bootcamp
Probably many vvvv novices owning Macs never bothered running Windows on their Macs, although it's quite easy to do so: Apple's free (being part of the OS) <a href="http://www.apple.com/support/bootcamp/" class="extURL" target="_blank">BootCamp</a> let's you run Windows OSes on almost all Intel based Macs. Running vvvv via BootCamp is  preferable to VM solutions, due to general performance disadvantages and some VMs lacking support for certain vvvv functionalities. Please read on if you're new to BootCamp on your Mac.   

## Windows7


Unless you need span mode or your (Intel) Mac lacks performance, I can safely recommend Windows 7 *64bit* (making use of all your RAM) and the latest iteration of BootCamp (at the time of writing 4.x for X's prior to 10.8.x and 5.x for 10.8.x onwards, <a href="http://www.apple.com/support/bootcamp/" class="extURL" target="_blank">read this</a> for official blurbs). The BootCamp Assistant (to be found at User/Applications/Utilities) of 10.7.x and later X's downloads the latest drivers onto a separate media (FAT32 formatted HD/USB Stick/...) provided by you. Windows 7 with said BootCamp drivers supports direct access (read only) to HFS volumes (ie. your Macintosh HD), eliminating the need of MacDrive and similar software. Make sure to update your BootCamp and graphics card driver to a recent version after completing BootCamp installation + check your settings within the BootCamp Control Panel. If you can't find it in the Task Bar or Windows Control Panels, refer to where you had BootCamp Assistant download the drivers and install manually.  

It's best practice to reformat your BootCamp partition to NTFS before having Windows Installer do it's job (you'll get a chance to do so before running the installation routine), avoiding potential installation failure. You *should* switch from FAT32 to NTFS later on (look that one up on the net), if you succeeded anyway.  

* Having trouble when installing XP via BootCamp, getting errors like missing dlls and/or media errors? "Boot up in OS X and create a FAT32 (max. 32GB) partition of your preferred size using BootCamp Assistant. Bear in mind that FAT32's max. partition size is 32GB."  

* Current BootCamp drivers are pretty much sophisticated, enabling two-finger secondary trackpad clicks, fn-key assisted choice of F-Key mapping, a proper Mac-style keyboard mapping and IR-Remote Control activation.  


## Windows XP and OS Xes prior to 10.6.x

1. Follow the instructions in Leopard's Boot Camp Assistant: insert the XP CD, reboot using BootCamp Assistant.
1. Follow the XP installation procedure. When you get to choosing the partition, you'll notice a partition called C: BOOT CAMP. Choose it.
1. XP installer will now ask you what to do with it. Format it. I used the full format option (as opposed to quick) and chose NTFS instead, which works fine. YOU NEED TO FORMAT THE DRIVE. OS X can't access NTFS, so why would I prefer NTFS instead of FAT32? NTFS is a superior file system, supports file sizes >4GB  and can be accessed on OS X running FUSE for OS X (http://osxfuse.github.com). Said to be working with 10.7.x. NTFS partitions are resizeable using BootCamp Assistant, Winclone and diskutil (in Terminal). 
1. 10.6.x supports direct access to NTFS volumes when following this procedure. It's somewhat experimental, sometimes not supporting external devices and officially considered to be unsafe. That being said, it worked for me and internal drives. Open up Terminal, type 
```  
sudo nano /etc/fstab  

```  
then add  
```  
LABEL=name none ntfs rw  

```  
where 'name' is the name of your Win partition. Reboot to get native read/write access to your NTFS partition or external drive.  

**Tired of erratic vertical two-finger scrolling using the track pad?**  
* *Try <span class="keyseq"><kbd>ALT</kbd></span> + two-fingers for smoother scrolling.*  

**Where's my middle-click on the track pad?**  
* *two-fingers on the track pad + <span class="keyseq"><kbd>SPACE</kbd></span> + track pad button*  

**What to do if you dislike the standard Apple keyboard layout on BootCamp?**  
* *Try <a href="http://www.olofsson.info/index.html?inputremapper.html" class="extURL" target="_blank">InputRemapper</a>.*  


## Backing up your BootCamp partition

How to backup your BootCamp (NTFS only) partition when Acronis reports errors or is just too cumbersome for the BootCamp novice?  
* *Try <a href="http://www.twocanoes.com/winclone/" class="extURL" target="_blank">WinClone</a> (running on OS X), NTFS only though. WinClone supports (safe) resizing of BootCamp partitions too. Version 3 isn't free anymore, but it's worth the buck.*  



*to be updated sporadically*