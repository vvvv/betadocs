---
uid: 45d8d0db-f5d4-409a-a9f1-ab44bdc0f711
---

# Change Log - vvvv45beta24.1
released on 06 10 10  
## general
* better error message when .net3.5 SP1 missing  
* no more error from nodebrowser when selecting local file via mouseclick  
* codeeditor had troubles being hidden via ALT+3 twice in sequence  
* fixed <a href="https://discourse.vvvv.org/t/gettransformpointergetcolorpointer-bug" class="extURL forum" target="_blank">gettransformpointergetcolorpointer-bug</a>  
* a vvvv_45betaXY directory can now again be moved on disk without stopping to work in the new place.  
* codeditor now works with effects as well  

## fixed nodes
* Timeliner loads data correctly again  
* Text (EX9) alignment and brush fixed  
* IOBox (Value Advanced) now merges subtypes when different nodes are connected downstream. The connection order will no longer be important. e.g. I (Spread) and Damper (Animation) connected to the Output of an IOBox will always result in a *Integer* IOBox.  

## new modules
* Line (EX9)  

## changed modules
* removed beattracker from AudioAnalysis (DShow9) due to licensing issues  