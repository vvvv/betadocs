---
uid: d7a193ec-160c-484d-9819-d202826c39aa
---

# Change Log - vvvv50beta39.1
released on 05 05 20  

## general
--- Installer now always asks for destination path  
--- Installer checks for running vvvv before installing/uninstalling  
--- fixed <a href="https://discourse.vvvv.org/t/beta39-framerate-drops-on-aws-ec2-instance/18095" class="extURL" target="_blank">issue with dropping framerate</a>  
--- fixed <a href="https://discourse.vvvv.org/t/trouble-getting-started-devvvveloping-plugin/18321/6" class="extURL" target="_blank">issue with OSC unpackChar</a>  
--- loaded packs now write correct pack info into patch files  
--- rightclick on file/dir IOBox no longer pops up context menu  
--- updated to latest RCP version (fixing issues with enums and userdata)  
--- fixed double node entries [https://discourse.vvvv.org/t/double-trouble-beta39/18005/4]  

## fixed nodes
--- fixed issue with SharedTexture (EX9.Texture) being broken  
--- fixed <a href="https://discourse.vvvv.org/t/tuio-encoding-array-out-of-bounds/18319" class="extURL" target="_blank">issue with TUIO nodes</a>  
--- Rekorder node now correctly hides borders in all cases  