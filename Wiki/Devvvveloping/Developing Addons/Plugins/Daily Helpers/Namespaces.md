# Namespaces

Libraries of classes are categorized using Namespaces. vvvv provides a small collection of useable classes, .net itself comes with a huge collection of ready to use classes.  

>note:  
If you use a namespace which is documented in one of the following class references and get an error after saving your plugin, you once have to add a reference to the namespace's dll in vvvv (see below).   
  


# The VVVV namespace

[Complete vvvv class library reference](TODO INTERNALLINK:/pluginspecs)  

Especially useful are:  
* **VVVV.Utils.VMath**: for all stuff not found in System.Math  
* **VVVV.Utils.Animation**: provides a Particle baseclass  


# The .NET namespace

<a href="http://msdn.microsoft.com/en-us/library/ms229335%28v=VS.90%29.aspx" class="extURL" target="_blank">Complete .net3.5 class library reference</a>  
<a href="http://msdn.microsoft.com/en-us/library/gg145045.aspx" class="extURL" target="_blank">Complete .net4.0 class library reference</a>  

Especially useful are:  
* **System.Collections.Generic**: List<T>, Dictionary<TKey, TValue>  
* **System.Collections**: IEnumerable  
* **System.XML**: for xml parsing and writing, xslt, xpath..and more  
* **System.IO**: for file reading and writing and filename and directory handling  


# Add a namespace's reference

![Add a namespace&#39;s reference](~/img/add_reference.png "Add a namespace&#39;s reference")   

* Open vvvv's ProjectExplorer by pressing ctrl+J and then navigate to your appropiate dynamic plugin within the shown list. The missing namespace which causes the error should also miss in the list entry 'References'.   
* Click right and add the reference as shown in the screenshot.  
