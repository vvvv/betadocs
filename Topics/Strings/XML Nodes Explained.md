---
uid: 3ffb0984-339d-4d17-8d70-822d6032744e
---

# XML Nodes Explained
Documents are represented by **Elements (aka Tags) and Attributes** - not strings, which helps *performance*...  

You can easily get some parts of your document and route those as a spread of Elements to other parts of your patch, where they get further analyzed.   

You always can convert an element to a simple string via <span class="node">AsString (Object)</span> - or back to an element via <span class="node">AsElement (XML)</span>. But typically you only want to do that once: when reading from disk or writing to disk. For the rest working with Elements and Attributes is much more comfortable since it allows to think of them in an object oriented manner.  

### Joining & Splitting 
There are nodes with which you can easily join & split XML-Elements (aka Tags) and Attributes: <span class="node">Element (XML Join)</span>, <span class="node">Element (XML Split)</span>, <span class="node">Attribute (XML Join)</span>, <span class="node">Attribute (XML Split)</span>.  

Note that by concatinating several <span class="node">Element (XML Split)</span> nodes - which also outputs an elements' child elements - will give you the possibility to dig into the xml structure. E.g. you could retrieve all child elements of an element, check its properties and dependant of some test select some of the childs via <span class="node">Select (Node)</span>. You therefore could patch a query into your xml structure...   
However this can get complicated and so we added some more nodes:  

### Handy nodes for analyzing XML
With GetElements & GetAttributes we added different ways of searching for child tags and attributes.   
When searching by name you get those that have a certain tag or attribute name and are direct child elements or attributes of the specified element.   
do that with <span class="node">GetElements (XML ByName)</span> & <span class="node">GetAttributes (XML ByName)</span>  


When searching by XPath you can express a more complex query that allows you dig deeper...  
do it with <span class="node">GetElements (XML ByXPath)</span> & <span class="node">GetAttributes (XML ByXPath)</span>  


While those nodes are flexible and spreadable in means of what you are searching for, they might be a bit unhandy when you already know that at a certain point in your patch only a certain tag with certain attributes are of interest.   

For those cases we added <span class="node">Prune (XML)</span> which lets you set those tag and attribute names statically in configuration pins with the bonus that you get friendly pin names and dont need to further process your attribute data.  


For being really sure that your patch system can work with a certain xml-File or string you can check validity with <span class="node">IsValid (XML RelaxNG)</span>. link: <a href="http://en.wikipedia.org/wiki/RELAX_NG" class="extURL" target="_blank">RelaxNG</a>   
Both XML Syntax (.rng-Files) & Compact Syntax (.rnc-Files) are supported.  