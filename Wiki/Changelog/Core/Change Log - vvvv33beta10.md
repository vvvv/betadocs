---
uid: 4a58b19b-64a8-4e20-958e-6f26318c2874
---

# Change Log - vvvv33beta10
released on 30 03 06  

## girlpower and modules
* WebInterface sample added  
* Mirror sample added  

## general
* FreeFrameWrapper now can cope with spreaded inputs (as used with the tracker nodes!)   
* Fanclub. the built in irc chat (Strg+F1) is working again  
* boygrouped renderers pop up as window again  
* press ALT while scrolling a patch to scroll horizontally. STRG and SHIFT speed up.  

## bug fixes
* FreeFrame nodes with outputs should crash less  
* * (3d Dot) and * (3d Cross) don't evaluate the second input pin  
* commandline arguments are interpreted correctly again  
* Renderer (HTML Url) pops up again  

* ScreenShot (EX9.Texture) working again  
* XFile (EX9.Geometry) spits out texturenames (only correct when relative paths)  
* Cons (EX9.Texture) in weired combinations with GetSlice upstream.  
* Line (EX9.Geometry) now works with a spread of binsizes  
* FileStream (DShow9) consumes much less power while paused  
* FormatValue (String) now always rounds correctly  
* Substitute (String) hangs less  
* IObox (Value Advanced): crashes less  
* Reader (File) : works more properly and reads files even if they are opened by another program  

## changed nodes
* XSLT (XML) now handles spreads  
* Writer (File) now can append strings to existing files  
* Separate (String) now has a Input "Keep Quotes" wich forces the parser to output the Quotes  
* XPath (XML) now can handle a spread of queries.  
* Normals (EX9.Geometry Mesh) now has a pin to specify a smoothing angle  
* Tidy (XML) now allows to specify the input- and output-character-encoding. There is also a new output-type "XMLNoHeader" which forces Tidy to strip XML- and Doctype-declaration.  
* HTTP (Network Get) now is spreadable. Also the in- and output-pins slidely changed.  

## new Nodes
* CreateEnum (Enumerations) allows to create own enum types  
* NULL (Enumerations) creates a pin which accepts any enum type. connect it to the OUPUT of a IOBox (Enumerations) to get an user enum inlet. also make use of Enum2Ord.  
* Styx (Windows) makes your system invulnerable.  
* HTTP (Network Post) sends data to given URLs using the HTTP-POST Method.  