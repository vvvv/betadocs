---
uid: 83dcbf3a-3b42-4f5e-a7d0-c35adbee817a
---

# change log - vvvv45beta30.2
released on 25 06 13  

## general
* code templates got a small cleanup  
* boygrouping "bridges" now streaming via fewer but bigger udp messages  
* fix for a XP bug introduced with beta30: <a href="https://discourse.vvvv.org/t/win-xp-b30-problems" class="extURL forum" target="_blank">win-xp-b30-problems</a>  

## code editor
* Fixed drawing performance issue - see <a href="https://discourse.vvvv.org/t/beta30-codeeditor-delay" class="extURL forum" target="_blank">beta30-codeeditor-delay</a>  
* Fixed CTRL-click on effect includes  
* Cloning a dynamic plugin didn't rename the *.cs file in beta30  

## changed nodes
* Kill (Windows) reimplemented as plugin (now non-blocking)  
* PID (Windows) revamped and renamed from PID (VVVV)  

## new nodes
* Resample (Spreads Gamma)  

## fixed nodes
* Writer (String) has append mode working again  
* LogFile (VVVV) works again  
* Renderer (TTY) no longer steals focus all the time  
* MidiSysexOutput (Devices) works again  
* TCP modules now have correct subtype range for <span class="pin">Port</span>  
* NodeBrowser (VVVV) works again as standalone  
* RS232 (Devices) will configure the port only if enabled  
* RS232 (Devices) will try to resume execution even if configuration of port fails for some properties - see <a href="https://discourse.vvvv.org/t/beta30-rs232-node" class="extURL forum" target="_blank">beta30-rs232-node</a>  
* Expr (Value) - fixed Sin/Cos/ArcTan in 64 bit - see <a href="https://discourse.vvvv.org/t/64bit-expr" class="extURL forum" target="_blank">64bit-expr</a>  
* Fixed <span class="pin">Mouse Wheel</span> in Mouse (System Window) - see <a href="https://discourse.vvvv.org/t/mouse-wheel-on-mouse-nodes-beta30" class="extURL forum" target="_blank">mouse-wheel-on-mouse-nodes-beta30</a>  
* FileTexture (EX9.Texture) fixed an issue with background loading:<a href="https://discourse.vvvv.org/t/filetexture-width-height-bug" class="extURL forum" target="_blank">filetexture-width-height-bug</a>  

## fixed modules
* Cursor (DX9) can handle a spread of mouse states now