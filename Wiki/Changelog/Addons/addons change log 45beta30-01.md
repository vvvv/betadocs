---
uid: b7432882-ae78-48dd-b750-f00e33b3f9e1
---

# addons change log 45beta30-01
released on 22 05 13  

## general
* enabled SSH, Facebook, ArduinoFirmata, RS232 and ShellExecute nodes in 64 bit build  
## new nodes
* AsXElement (JSON) as pendant to AsXElement (XML)  
## changed nodes
* updated bindings of <span class="node">HTMLTexture (Ex9.Texture)</span> to latest released CEF 1.1364.1123 (see <a href="http://code.google.com/p/chromiumembedded/" class="extURL" target="_blank">official website</a> for a complete list of changes)  
* [node:FirmataEncode](TODO INTERNALLINK:node:FirmataEncode)/[node:FirmataDecode](TODO INTERNALLINK:node:FirmataDecode) support Capability reports (request and show) that show your boards available pins and their respective modes + resolution  
* <span class="node">Arduino (StandardFirmata 2.x)</span> reflects changes of above + uses updated [node:RS232](TODO INTERNALLINK:node:RS232) which offers a way to bypass the autorest on most arduino boards.  
* TobiiEyetracker nodes (Browser, Headbox, XConfig, Tracking, Eyetracker, Calibration). For using Tobii eyetracking devices.  
## fixed nodes
* <span class="node">HTMLTexture (Ex9.Texture)</span>  
  * crashed when doing fast url switching (see [here)](https://vvvv.org/forum-alpha/html-texture-performance): fixed by blocking until internal used CEF browser object (used by each slice of a renderer) is created.  
  * crashed when decreasing the width/height inputs (see <a href="https://discourse.vvvv.org/t/htmltexture-bugs-driving-me-crazy" class="extURL forum" target="_blank">here</a>): fixed by doing an intersect for each dirty rectangle reported by cef before writing to the texture.  
  * crashed when setting new "Update DOM" pin to true: should be fixed by new blocking behaviour in constructor.  
  * fixed various issues in CefXmlReader (used to translate CefDom to XDocument/XElement).  
* MIDI module fixes  
  * normalised MidiNoteOut, MidiControllerOut, MidiProgramOut to consistently use channels 0-15 on pins.   
  * fixed incorrect channel mappings.   
  * resetting the channel pin does not result in setting a value of 0.5.