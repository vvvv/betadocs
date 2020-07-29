---
uid: d377780f-4761-4137-8c5c-cdf890882d74
---

# Plain Text files

<a href="http://en.wikipedia.org/wiki/Plain_text" class="extURL" target="_blank">Wikipedia on Plain Text</a>  
<a href="http://en.wikipedia.org/wiki/Character_encoding" class="extURL" target="_blank">Wikipedia on Character Encodings</a>  
<a href="http://en.wikipedia.org/wiki/Unicode" class="extURL" target="_blank">Wikipedia on Unicode</a>  
#### Related nodes
<span class="node">Reader (String)</span>  
<span class="node">Writer (String)</span>  



vvvv uses Unicode internally but it allows you to read and write plain text files in *any* encoding you like.   

Plain Text files are good for:  
* saving texts  
* saving values in a human-readable form  

Their weakness:  
* big size of the files  
* conversion of values into characters & loosing precision  

Files that contain markup or other meta-data are generally considered plain-text.   

* Simple peers like <a href="http://en.wikipedia.org/wiki/Comma-separated_values" class="extURL" target="_blank">CSV</a> can be parsed using the nodes from the [String category](xref:12388a90-72f1-415d-892d-a63403ffedd3).  
* For XML files use the [XElement nodes](xref:e340b940-5084-40c4-899c-ed1021135b81).  
* For a bit more advanced pattern matching use [Regular Expressions](xref:899eb389-4a32-4633-a0dd-be489220b0b3).  

Examples in your vvvv\girlpower\ directory:  
* \IO\Files  

**See also:**  
* [String category](xref:12388a90-72f1-415d-892d-a63403ffedd3)  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/8112+3419" class="extURL" target="_blank">Related Contributions</a>  



