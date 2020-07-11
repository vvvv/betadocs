---
uid: b43c8ad4-1367-4f68-a3c5-5d76637b241b
---

# String encodings in vvvv
Using vvvv we mostly don't have to worry about the mess of character encodings at all, since it simply uses unicode. Only when reading/writing to/from files or sending/receiving a string via the network you'll have to specify an encoding. Still here is a bit of history:  

# Before Unicode
In the beginning there was <a href="https://en.wikipedia.org/wiki/Ascii" class="extURL" target="_blank">ASCII</a>, a 7bit encoding that includes definitions for 128 characters (33 of which are non-printing <a href="https://en.wikipedia.org/wiki/Control_character" class="extURL" target="_blank">control characters</a>). But those 128 symbols were obviously not enough to represent all of the worlds languages and therefore different organizations started to define their own (mostly 8bit) character encodings (also referred to as <a href="https://en.wikipedia.org/wiki/Code_page" class="extURL" target="_blank">code pages</a>) that allowed them to represent more different symbols each.   

This lead to a big naming-mess which is hard to grasp in its entirety as this attempt to compile a <a href="http://www.firstobject.com/character-set-name-alias-code-page.htm" class="extURL" target="_blank">listing of codepages and their aliases</a> shows. One popular codepage for example runs by the following names:  

>**Western European (Windows)**, 1252, Windows-1252, x-ansi, CP1252, MS-ANSI  
not to be confused with:  
>**Western European (ISO)**, 28591, iso-8859-1, cp819, Latin1, ibm819, iso_8859-1, iso_8859-1:1987, iso8859-1, iso-ir-100, l1, csISOLatin1  
which basically defines the same, but some less characters.   

To add to the confusion Microsoft now calls the "Windows Code Pages" what were formerly know as the <a href="https://en.wikipedia.org/wiki/Windows_code_page#ANSI_code_page" class="extURL" target="_blank">ANSI Code Pages</a>. And the simple term *ANSI* is still often used synonymously for "single-byte encoding" which can be interpreted (for display) by applications as any single-byte codepage, typically the one that is specified via the <a href="https://en.wikipedia.org/wiki/Locale" class="extURL" target="_blank">locale setting</a>) of the operating system.  

This had to be sorted. Enter *Unicode* the one-fits-all universal character set.  

# Unicode
A simple idea but another naming-fiasco. Talking "unicode" is only half of the story. The term itself only denotes the character set which holds all the characters you can imagine and assigns a unique <a href="https://en.wikipedia.org/wiki/Codepoint" class="extURL" target="_blank">code point</a> to each of them. So instead of the incomprehensible number of different 8bit codepages there is now one large character set that can uniquely address 1.114.112 different code points in 17 <a href="https://en.wikipedia.org/wiki/Plane_%28Unicode%29" class="extURL" target="_blank">planes</a> of 2^16 characters each (only a fraction of which is actually assigned by now). The first plane goes by the name <a href="https://en.wikipedia.org/wiki/Plane_%28Unicode%29" class="extURL" target="_blank">Basic Multilingual Plane (BMP)</a> and consists of code points in the range of U+0000 to U+​FFFF (just so you have heard about that, nothing to worry about really).  

Nothing has been said so far about how a series of such code points can be made into a sequence of bytes for saving strings or sending them via the network. This is what **encoding schemes** are for. Different <a href="https://en.wikipedia.org/wiki/Utf" class="extURL" target="_blank">Unicode Transformation Formats (UTF)</a> exist that describe the ordering of bytes that make up a unicode string. So when facing a unicode string the relevant question is the one after its encoding. Luckily nowadays the answer most likely is: UTF-8.  

While at first glance that name may give the impression that it uses 8bits to encode characters, UTF-8 is actually a <a href="https://en.wikipedia.org/wiki/Variable-width_encoding" class="extURL" target="_blank">variable width encoding</a> scheme that uses up to 4 code units (with a size of 8bits each) to encode any character. One speciality of UTF-8 is that it encodes all of the ASCII characters using one byte only therefore being compatible to plain ASCII encoding.   

Still the question remains how, given a string, one could find out about its encoding. While there is the concept of the <a href="https://en.wikipedia.org/wiki/Byte_order_mark" class="extURL" target="_blank">Byte Order Mark (BOM)</a>, a series of leading bytes in a string to signify its encoding is used for <a href="https://en.wikipedia.org/wiki/UTF-16" class="extURL" target="_blank">UTF-16</a> (formerly known as UCS-2) encodings, its use is <a href="https://en.wikipedia.org/wiki/Byte_order_mark#cite_note-2#cite_note-2" class="extURL" target="_blank">neither required or recommended</a> for UTF-8. Leaving a parser to guess at a string that has none of the UTF-16 BOMs but still contains bytes higher than the ASCII range to be UTF-8 encoded.   

For xml-documents e.g the encoding is supposed to be specified in the first tag of its content, like:  
 <?xml version="1.0" encoding="UTF-8"?>


# Links
<a href="http://www.joelonsoftware.com/articles/Unicode.html" class="extURL" target="_blank">The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)</a> by Joel Spolsky  
<a href="https://en.wikipedia.org/wiki/Unicode" class="extURL" target="_blank">Wikipedia on Unicode</a>  
http://www.unicode.org  
<a href="http://notepad-plus-plus.org/" class="extURL" target="_blank">Nodepad++</a> free text editor with flexible encoding options