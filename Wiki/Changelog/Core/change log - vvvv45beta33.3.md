---
uid: d29ac05a-a025-4577-a156-4a76f564835d
---

# change log - vvvv45beta33.3
released on 09 10 14  

## general
* major performance, see <a href="https://discourse.vvvv.org/t/performance-drop-from-beta31.2x64-to-beta33.1x64" class="extURL forum" target="_blank">performance-drop-from-beta31.2x64-to-beta33.1x64</a>  
* fix for: <a href="https://discourse.vvvv.org/t/undo-doesnt-work-on-links" class="extURL forum" target="_blank">undo-doesnt-work-on-links</a>  
* the RS232 COM port enum will be registered on startup  

## new node
* Entries2String: that lists all entries of a given enum as a spread of strings  

## changed nodes
* AsRaw (EX9.Texture) now has an actual RAW option  

## fixed nodes
* Dir (File) sometimes reported wrong files, see (<a href="https://discourse.vvvv.org/t/dir-%28file%29-outputs-file.foo-at-the-correct-spreadsize." class="extURL forum" target="_blank">dir-%28file%29-outputs-file.foo-at-the-correct-spreadsize.</a>  
* fixed Unzip (String) node not updating its output when changing the count pin  
* Renderer (EX9): fix for when disabled and connected to DX9Texture <a href="https://discourse.vvvv.org/t/behaviour-change-of-disabled-renderer-%28ex9%29-%3E%3D-beta33-%28?full=1" class="extURL forum" target="_blank">behaviour-change-of-disabled-renderer-%28ex9%29-%3E%3D-beta33-%28?full=1</a>  


