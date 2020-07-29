---
uid: cc1de49b-a377-4b72-bb0f-b800039e84bc
---

# change log - vvvv45beta31
released on 28 08 13  

## general
* Error view of code editor will include error number now <a href="https://discourse.vvvv.org/t/beta30-codeeditor-delay" class="extURL forum" target="_blank">beta30-codeeditor-delay</a>  
* Handle of HID devices weren't properly closed in some cases <a href="https://discourse.vvvv.org/t/device-enumerating-related-errors" class="extURL forum" target="_blank">device-enumerating-related-errors</a>  
* fixed crash of 64-bit-vvvv when dealing with memory intensive patches  

## fixed nodes
* OSCDecoder (Network) finally deals with patterns  
* HIDEncode/Decode can now handle pins with equal names  
* SharedMemory (Windows) works in x64 build: <a href="https://discourse.vvvv.org/t/sharedmemory-(windows)-not-working-in-45beta30.2x64" class="extURL forum" target="_blank">sharedmemory-(windows)-not-working-in-45beta30.2x64</a>  
* GlyphInfo (String) re-evaluates correctly: <a href="https://discourse.vvvv.org/t/glyphinfo-re-evaluate-bug" class="extURL forum" target="_blank">glyphinfo-re-evaluate-bug</a>  
* Find (String) works in 'all' mode: <a href="https://discourse.vvvv.org/t/find-(string)-bug" class="extURL forum" target="_blank">find-(string)-bug</a>  
* Player (EX9.Texture) fixed file extension casing issue and improved playback performance of dds files: <a href="https://discourse.vvvv.org/t/player-(ex9.texture)-doesnt-work-with-files-created-with-ati-compressonator" class="extURL forum" target="_blank">player-(ex9.texture)-doesnt-work-with-files-created-with-ati-compressonator</a>  
* Fixed support for multiple texture coordinates in collada loader: <a href="https://discourse.vvvv.org/t/multiple-texcoords-from-collada-not-working" class="extURL forum" target="_blank">multiple-texcoords-from-collada-not-working</a>  
* Decode (Raw Base64) didn't mark output as changed  
* Reader (Raw) will use proper sharing mode now: <a href="https://discourse.vvvv.org/t/reader-%28raw%29-doesnt-read-files-that-are-opened-by-another-programprocess" class="extURL forum" target="_blank">reader-%28raw%29-doesnt-read-files-that-are-opened-by-another-programprocess</a>  
* Fixed range check error in Sort (Spreads) node  
* VertexBuffer (EX9.Geometry Split) supports more color formats now (float1-4, T3DColor): <a href="https://discourse.vvvv.org/t/mesh-split-messes-up-vertex-colors" class="extURL forum" target="_blank">mesh-split-messes-up-vertex-colors</a>  

## changed nodes
* ColladaFile (EX9.Geometry) got a reload pin  
* Mesh (EX9.Geometry Collada) outputs mesh name, mesh path, and material name  
* Prune (XElement) now takes complete xpath expressions to generate output pins. please update your patches.  
* Leap (Devices) can output gestures  
* added Gesture split nodes for Leap  

## plugin interface
* Fixed issue with high spread counts and multi dimensional streams:<a href="https://discourse.vvvv.org/t/unzip-%28bin%29-wrong-sorting-on-high-spreadcounts" class="extURL forum" target="_blank">unzip-%28bin%29-wrong-sorting-on-high-spreadcounts</a>  