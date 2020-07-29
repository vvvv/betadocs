---
uid: 6ef4f8dd-ac2d-4c50-b1f2-c4841ffb5518
---

# Change Log - vvvv40beta19.1
released on 14 11 08  

## general
* ctrl+m fixed (no longer saves multiple INFO tags)  
* output-stringpin-tooltips no longer freeze vvvv  <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=12950&topics_threshold=0&topics_offset=290&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">link</a>  
* Shortcuts working again after opening patches with docked plugins. as noted <a href="http://vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=23003" class="extURL" target="_blank">here</a>  
* no more nasty popup on startup concerning file-type registration if you are no admin  

## fixed nodes
* FileStream (DShow9) now deals correctly with urls as filename  
* Writer (EX9.Texture) no longer saves files with double fileextension  
* Renderer (Flash): fixed playback of files as pointed out <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=22805&topics_threshold=0&topics_offset=3&topics_sort_mode=lastPost_desc&topics_find=&forumId=12" class="extURL" target="_blank">here</a>  

## modules
* ALL modules got a good help file, tags for future search functions, taglines for future tooltips in node menus  
* invented an open place where all modules will be collected: <a href="https://vvvv.svn.sourceforge.net/svnroot/vvvv/modules/trunk" class="extURL" target="_blank">somewhere on sourceforge</a>. somehow contact the vvvv group to get an account.  
* new folder structure for all shipped modules  
* renamed some modules, however they will be properly converted 