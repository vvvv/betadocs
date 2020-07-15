---
uid: 16491d30-9b16-48d5-8ad1-74ca43a2c1dd
---

# Addonpack Plugins
Here is how you prepare your plugins for the addonpack:  

## Provide a Node Info
Make sure to provide a meaningful description for your nodes via the [plugininfo attributes](xref:29a92e37-7494-441d-93f7-36beeb1a0f2e)  

This information will help users find/choose nodes in the NodeBrowser and in the [node reference](https://vvvv.org/documentation/node-reference).  

## Follow the conventions
* [Conventions.CodingStyle](xref:dfa9f04a-bfbb-41b9-b475-36031d9085ed)  
* [Conventions.NodeAndPinNaming](xref:db8592a2-03c3-4e8c-a540-d11df5e83078)  

## License/Credits
If your plugin is based on an external library or code that has a license attached, please don't forget to mention that. put the license in a file called:  
 license-mypluginname.txt 
and place it in your plugins directory. from there the buildprocess will automatically copy it to \plugins\licenses for the enduser to see.  

## Help patch
Please make sure to consult [Conventions.HelpPatch](xref:07824e2d-da59-4df0-9f49-a143dc0f7625) and place a correctly named help patch in the lib\nodes\plugins directory.   

