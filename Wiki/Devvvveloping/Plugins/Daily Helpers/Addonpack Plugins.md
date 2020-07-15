---
uid: 16491d30-9b16-48d5-8ad1-74ca43a2c1dd
---

# Addonpack Plugins
Here is how you prepare your plugins for the addonpack:  

## Provide a Node Info
Make sure to provide a meaningful description for your nodes via the [plugininfo attributes](TODO INTERNALLINK:plugininfo attributes)  

This information will help users find/choose nodes in the NodeBrowser and in the [node reference](https://vvvv.org/documentation/node-reference).  

## Follow the conventions
* [Coding style guidlines](TODO INTERNALLINK:Conventions.CodingStyle)  
* [Node and pin naming guidlines](TODO INTERNALLINK:Conventions.NodeAndPinNaming)  

## License/Credits
If your plugin is based on an external library or code that has a license attached, please don't forget to mention that. put the license in a file called:  
 license-mypluginname.txt 
and place it in your plugins directory. from there the buildprocess will automatically copy it to \plugins\licenses for the enduser to see.  

## Help patch
Please make sure to consult [Conventions.HelpPatch](TODO INTERNALLINK:Conventions.HelpPatch) and place a correctly named help patch in the lib\nodes\plugins directory.   

