---
uid: 72467aac-c844-40fa-8ef4-a44548354378
---

# change log - vvvv45beta32.1
released on 12 06 14  
## general
* fix on client side treatment of half boygrouped modules  
* fixed mainloop settings for thread timer <a href="https://discourse.vvvv.org/t/mainloop-works-differently-in-beta32" class="extURL forum" target="_blank">mainloop-works-differently-in-beta32</a>  

## gui
* fixed <a href="https://discourse.vvvv.org/t/middle-click-on-pins-not-always-working" class="extURL forum" target="_blank">middle-click-on-pins-not-always-working</a>  
* fixed <a href="https://discourse.vvvv.org/t/middle-click-to-create-iobox-no-longer-brings-up-the-iobox-options-menu-when-starting-the-conn" class="extURL forum" target="_blank">middle-click-to-create-iobox-no-longer-brings-up-the-iobox-options-menu-when-starting-the-conn</a>  
* fixed <a href="https://discourse.vvvv.org/t/glitches-in-node-browser" class="extURL forum" target="_blank">glitches-in-node-browser</a>  
* fixed Ctrl+G issue introduced in b32  

## fixed nodes
* FileTexture (EX9.Texture) works with pipet again  
* Icon (Windows) working on win8 now  
* IRC (Network Open) can send channelmessages again  
* the Index pin of the Keyboard and Mouse (Devices Desktop) nodes is now set to -1 by default, which merges all available devices into one  
* fixed Player (EX9.Texture) when new texture format pin was set to "No Specific" and format of input file wasn't supported on graphics card - see <a href="https://discourse.vvvv.org/t/player-(ex9.texture)-glitches-images-in-beta32" class="extURL forum" target="_blank">player-(ex9.texture)-glitches-images-in-beta32</a>  

## new nodes
* <span class="node">PointEditor (3D Boygrouped Persistent)</span> added - replaces sandwich  
* <span class="node">GridEditor (EX9 Boygrouped)</span> added - replaces sandwich  

## plugin interfaces
* fixed IDiffSpread.IsChanged inconsistency between b31.2 and b32 - see <a href="https://discourse.vvvv.org/t/inconsistent-behaviour-between-ischanged-in-v1-and-v2-pins" class="extURL forum" target="_blank">inconsistent-behaviour-between-ischanged-in-v1-and-v2-pins</a>  
* fixed <a href="https://discourse.vvvv.org/t/asstring-(object)-and-or-getslice(node)-issue-with-xelement-in-beta32-x86-x64" class="extURL forum" target="_blank">asstring-(object)-and-or-getslice(node)-issue-with-xelement-in-beta32-x86-x64</a>