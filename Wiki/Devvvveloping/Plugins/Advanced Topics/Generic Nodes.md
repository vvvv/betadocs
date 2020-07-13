---
uid: a4ee0097-c57b-4788-822f-a7b07953e5a1
---

# Generic Nodes
There are several nodes in vvvv which are programmed in a generic way. This means that the functionality is defined once in the project *GenericNodes* and every developer can get over 20 nodes with just some clicks for his own data type.  

You can browse the nodes and their source code here: <a href="https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/src/core/GenericNodes" class="extURL" target="_blank">Generic Nodes on github</a>  

# Source Code Structure

Most generic nodes are pure spread operations and do not need to know anything about the type on which they operate, we called them *basic* nodes. However, there are some nodes which need to check whether two instances are equal in order to execute their functionality. Other, more specialized nodes need to *clone* an instance or calculate the *distance* between two instances of the type on which they operate.  

We decided to sort the source code according to the method which is required for the data type, so each developer can decide which nodes make sense for his data type.  

Every generic node definition should be in its own file and should be located in the folder with the name of the method it needs to operate.  

# Adding nodes for you own data type

First reference the GenericNodes project in your own project. Either use the <a href="https://vvvv.org/blog/nuget-development-packages" class="extURL blog" target="_blank">nuget package</a> or the project directly if you are working in the Addonpack.sln. Then the only thing you have to do is to copy the code from our template files and replace the string 'REPLACEME_CLASS' with your own data type and the string 'NODECATEGORY' with the category in which the nodes should land in the node browser.  

For example, if your type is called *BooleanShape* in the category *BooleanGeometry* then the Cons node would look like this:  

```  
	[PluginInfo(Name = "Cons",
                Category = "BooleanGeometry",
                Help = "Concatenates all input spreads to one output spread.",
                Tags = "generic, spreadop"
                )]
    public class BooleanGeometryConsNode : Cons<BooleanShape> {}

```  

We even made an easy to use convvvverter patch which does this for you. It is also located in the GenericNodes project and called *TemplateConvvvverter.v4p*. Open it and follow the instructions in the patch.  

# Contributing a new Generic Node

If you have a generic node which you want to add to the GenericNodes project, fork  the vvvv-sdk sources on github and add the generic node in the same way as the other ones:  

1.) Create a .cs file named after your node in the folder with the name of the method you need for the node.

2.) Add a dummy instantiation of your node to the template files

3.) Open a pull request from your fork

If the method you need for your node doesn't exist, create a new folder and a new template file with the same naming convention.