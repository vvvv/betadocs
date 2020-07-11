---
uid: 416e8b90-1f8e-4082-a5ad-c58891d8455a
---

# Writing Freeframe Plugins
The following tutorial guides you step by step to create your own video effect plugins based on the <a href="http://www.freeframe.org" class="extURL" target="_blank">freeframe</a> 1.0 standard and vvvv.org’s extended freeframe specification, which allows you to return values from video plugins.   

## 1. vvvv & FreeFrame
As of this writing there are two official versions of freeframe:  
* 1.0   
* 1.5   
and one unofficial:  
* 1.0-Extended (by vvvv.org)  

<a href="http://freeframe.sourceforge.net/spec.html" class="extURL" target="_blank">Freeframes original 1.0 specification</a> is solely targeted at plugins for videomanipulation. With only minor extensions to that specification the framework is also suitable for plugins that do analysis on a video image and report back data found. The [Extended FreeFrame Specification](TODO INTERNALLINK:FreeFrameExtendedSpecification) describes all the additions to the 1.0 specification that allow plugins to not only receive simple value inputs but also receive and return spreads of values.  

vvvv does not fully implement all functionality that freeframe offers:  

### Source Plugins
Freeframe has the notion of *Source Plugins*, i.e. plugins that generate video based on input parameters. In vvvv such plugins will still need any dummy video connected to the input in order to generate output.  

### Multiple Inputs
While in the field freeframe plugins can have multiple inputs DSFreeFrameWrapper/vvvv only support one-input plugins.   

### FFGL (FreeFrame 1.5)
The latest developments in freeframe feature an opengl/shader based implementation of plugins. Since vvvv is based on Direct3D and already has a simple interface for shaders via [ex9-rendering](TODO INTERNALLINK:ex9-rendering) FFGL will probably not be an issue here soon.  

## 2. FreeFrame plugins in a DirectShow graph
Before we start coding....A simple way of browsing through a list of freeframe plugins is using a tool like Graphedit in connection with the DSFreeFrameWrapper <a href="http://en.wikipedia.org/wiki/DirectShow" class="extURL" target="_blank">DirectShow</a> filter.   

<a href="http://en.wikipedia.org/wiki/GraphEdit" class="extURL" target="_blank">Graphedit</a> is an ugly tool provided by Microsoft for prototyping directshow graphs. After many years of pain finally two opensource initiatives emerged that are working on reimplementations and improvements of graphedit: <a href="http://blog.monogram.sk/janos/tools/monogram-graphstudio/" class="extURL" target="_blank">GraphStudio</a> and <a href="http://www.codeproject.com/KB/audio-video/dsgraphedit.aspx" class="extURL" target="_blank">DSGraphEdit</a>  

In order to use a freeframe plugin within a DirectShow graph the DSFreeFrameWrapper filter is needed. This wrapper sits in the graph and can load one freeframe plugin at a time. Everytime a directshow mediasample arrives it hands over the pointer of the current image to the freeframes    
 processFrame() 
function. After the plugin is finished manipulating the image DSFreeFrameWrapper hands the mediasample further down the graph.   

<a href="http://freeframe.cvs.sourceforge.net/freeframe/DSFreeFrameWrapper/" class="extURL" target="_blank">DSFreeFrameWrapper is opensource</a> under the BSD license and can thus be used freely in any application. It also ships with vvvv in the \bin directory. So if  you had vvvv running at least once on your machine DSFreeFrameWrapper is already registered and available in the system.   

Creating directshow graphs with tools like graphedit is easy. They all offer lists of all filters available in the system. There you chose a source filter, like a filestream or a capture device and the DSFreeFrameWrapper to insert in the graph. Rightclicking on the source filters output will offer you to *Render* that pin, which will automatically connect the available pins and insert further needed ones to setup a fully working graph.  

A simple directshow graph including DSFreeFrameWrapper would look like this:  

![](~/img/dsfreeframewrappergraph.png "")  

Running the graph will now simply show the source video. Rightclick DSFreeFrameWrapper and open its property page. Here you can select a directory of freeframeplugins and then quickly browse through all available plugins by scrolling your mousewheel after having selected the pulldown that holds all the individual plugin .dlls.  

## 3. The CodeBlocks IDE
<a href="https://sourceforge.net/projects/freeframe/" class="extURL" target="_blank">sourceforge/freeframe</a> hosts SDKs for developing plugins with Delphi, Visual Studio and XCode. In this tutorial we'll use the free C++ IDE <a href="http://www.codeblocks.org" class="extURL" target="_blank">CodeBlocks</a> to compile our code. It is lightweight, and has all we need. From the <a href="http://www.codeblocks.org/downloads/5" class="extURL" target="_blank">downloads section</a> get the version with MinGW which includes the free gcc compiler. Alternatively codeblocks will detect any already installed compilers on your system and offer you to use those.   

## 4. Version Control
If you are not familiar with the practice of Version Control, please read a short introduction to [Version Control with Subversion](TODO INTERNALLINK:Version Control with Subversion) before continuing, as you else may miss some concepts/terms we'll be referring to below.  

All code you need to develop freeframe plugins is available from public subversion repositories on <a href="http://sourceforge.net" class="extURL" target="_blank">http://sourceforge.net</a> So this is where we now get a basic template from to start coding.  

## 5. A simple Template
Assuming you have TortoiseSVN already installed create a new directory called something like:  
 \dev\freeframes\Template
and rightclick it to *SVN Checkout*  
 https://vvvv.svn.sourceforge.net/svnroot/vvvv/freeframe/CodeBlocks/Template/trunk

Simply enter this url in the *URL of Repository* field and press ok. This will fill you Template directory with the source files of the template freeframe effect.  

Now start CodeBlocks and open the Template.cbp file. Use CTRL+F9 to build the project and if everything went well the Log should finish with the line:  
 0 errors, 0 warnings

In your \Template directory there is now a new file called *Template.dll*, which is an actually working freeframe plugin. Start vvvv and dragdrop the .dll onto the patch. Voila.   

Connect VideoIn and VideoOut nodes to the plugin and see it in action. The first pin on a freeframe plugin node is always the video input. The last pin is the *Enabled* pin with which you can always disable effects processing and simply pass the video through. All the pins in between those two are the effects parameters. In the Templates case there are 3 pins to control the intensities of the videos RGB values.  

>note:  
The Template project consists of only 2 source files and their headers:  
* The heart of every freeframe plugin is the FreeFrame.cpp file. This  file effectively implements the freeframe specification.  
* Template.cpp contains the implementation of an actual plugin.  
  

## 6. My First FreeFrame
Now that we know that the template works, instead of modifying it we make a copy first to keep the template a template. So just copy your  
 \dev\freeframes\Template
directory to something like:  
 \dev\freeframes\MyFirstFreeFrame

>note:  
Don't forget to delete the hidden \.svn directory within your new  directory, as it holds subversion info for the original template directory which is no longer valid for your copy!  
  

In CodeBlocks now open the Template.cbp from your new directory, press CTRL+F9 to build, start vvvv, drop the Template.dll into the patch, attach VideoIn and VideoOut and save the patch into your developing directory.   

For a convenient debugging setup you now can specify this patch to start everytime you *run* your plugin in CodeBlocks. Go to *Project* select *Set programs' arguments..*: In the host application field specify a full path to vvvv.exe and in the program arguments field put something like:  
 /o D:\dev\MyFirstFreeFrame\Tester.v4p
Now on pressing F9 vvvv starts with the specified patch.  

### Customizing the Template
First it makes sense to rename the project and the actual plugin files. In the Projects tab righclick the projectname and select *Properties*. Here you can specify a new project title. In the second tab (Build Targets) you can change the name of the .dll to be created.   
Then make sure all source files are closed and rightclick Template.cpp and  Template.h to rename them to your own liking.   

### FreeFrame.cpp
The only thing you have to change in FreeFrame.cpp is to set an include to your plugins header file right below include of FreeFrame.h, like this:  
```c  
1. include "MyFirstFreeFrame.h"
```

### MyFirstFreeFrame.h 
Here you set the number of input parameters you'll use via this define:  
```c  
1. define NUM_PARAMS 3
```

Define functions and variables private to the plugin in the private section of the *plugClass* class.  
```c  
class plugClass  
{  
  public:   //leave code in this section as is
  private:  //your variables and functions here
}
```  

### MyFirstFreeFrame.cpp
Here we've finally reached the interesting parts of the code. First make sure to define an include for your header file right below the initial commens, replacing the Template.h include, like this:  
```c  
1. include "MyFirstFreeFrame.h"
```

Following are some structs to fill out with your plugins info.   

 PlugInfoStruct* getInfo()
The GPlugInfo struct needs the following information:  
 .ApiMajorVersion (for now only 1 is allowed)
 .ApiMinorVersion (vvvv only supports 0)
 .uniqueID (a unique string of 4 characters)
 .pluginName (a 17 character pluginname, the actual vvvv-node name)
 .pluginType (vvvv only supports FF_EFFECT)

 LPVOID getExtendedInfo()
selfexplaining. not really important for now. can leave this as is.  

 DWORD getPluginCaps(DWORD index)
FreeFrame plugins can offer different treatment for 16, 24 and 32bit video. Choose what you need. Typically only 24 bit makes most sense. The plugin can also specify if it needs a copy of the incoming image or can operate on the source image directly. With vvvv you'll always work on the input directly, so you can leave this as is.  

Now initialisation of the plugin specific data structures follows, which is devided into two steps:  
* Initialisation (static plugininfo like inputnames, types,..)  
* Instantiation (plugin-instance specific data)  

 DWORD initialise()
Just as the template demonstrate here you specify types, defaults and names for all your inputs. The <a href="http://freeframe.sourceforge.net/spec.html" class="extURL" target="_blank">FreeFrame Specification</a> lists all the possible parameter types.  

 DWORD deInitialise()
Couterpart to initialize(), most likely not used.  

 LPVOID instantiate(VideoInfoStruct* pVideoInfo)
Here the actual instance of the plugin is created. Leave this as is for now.  

 DWORD deInstantiate(LPVOID instanceID)
Couterpart to instantiate(). Leave as is.  

Okokok. Here we are:  
 DWORD plugClassprocessFrame24Bit(LPVOID pFrame)
This is the one function that operates on the actual image and is called for you every frame. You can see that actually processFrame() is called every frame which decides which function to call depending on the current videos bitDepth. In most scenarios you'll only operate on 24bit.   

The incoming parameter *pFrame* is a pointer to a simple struct:  
```c  
typedef struct VideoPixel24bitTag {  
 BYTE blue;
 BYTE green;
 BYTE red;
}
```  

As the template suggests this is the place to go through all the pixels and paint them as you feel they should look. You can access the plugins input parameters via the FParams[] array which holds their current values in the order as you specified them in *initialse()*.   

## 7. A FreeFrame 1.0-Extended Template
A simple template including all the additions from the Extended specification in FreeFrame.cpp and FreeFrame.h is available from here:  
 https://vvvv.svn.sourceforge.net/svnroot/vvvv/freeframe/CodeBlocks/TemplateExt/trunk

Here the important additions in detail:  
 DWORD setThreadLock(DWORD Enter);
As directshow runs in separate thread to vvvv, reading data from the plugin (which via DSFreeFrameWrapper also is in that separate thread) needs to be synchroniced. All you have to make sure is to call:  
 EnterCriticalSection(&CriticalSection);
at the beginning of processFrame() and   
 LeaveCriticalSection(&CriticalSection);
at its end, as TemplateExt shows. Do all the analysis and calculation of output data within the critical section to stay in sync.  

 DWORD getOutputSliceCount(DWORD index);
This is where you have to return the SliceCount for the output specified via the incomming index parameter in order for the host application to know what it has to expect.  

 float* getOutput(DWORD index);
Here you return a pointer to the float the actual data spread.  

 DWORD setInput(InputStruct* pParam);
This is called for every spread that is set to the plugin.  

## 8. A Template using OpenCV
Image analysis is a tough job and thanks to some fine open-source libraries we don't have to reinvent the wheel in many cases. One very popular library for computervision containing a large amount of useful code is the <a href="http://opencvlibrary.sourceforge.net/" class="extURL" target="_blank">OpenCV</a> library.   

OpenCV can easily be used within freeframe plugins and here is a template that provides an easy starting point for that scenario:  
 https://vvvv.svn.sourceforge.net/svnroot/vvvv/freeframe/CodeBlocks/TemplateExtOpenCV/trunk

After <a href="http://sourceforge.net/project/showfiles.php?group_id=22870&package_id=16937" class="extURL" target="_blank">downloading OpenCV_1.0</a> and installing it you need to set a windows environment variable *OpenCV* to point to the installation directory, like:  
 OpenCV = "C:\Program Files (x86)\OpenCV" 
* note that environment variables are case-sensitive  
* don't forget the quotes if your path has spaces  
* make sure to restart CodeBlocks in case you already had it open  
Opening the TemplateExtOpenCV.cbp project now should compile without errors. In case you have troubles with the paths here is where to check in the projects Build Options:  
* *Linker settings* tab:  
* *Search directories* tab and there on the *Compiler* tab  
In those places paths to OpenCV have to be set correctly.  

The processFrame() function exemplarily uses OpenCV functions. Starting from here you'd probably want to dive into <a href="http://opencvlibrary.sourceforge.net/#head-68bf1619b36f7064dbb9dbfecc272901ee8baf42" class="extURL" target="_blank">OpenCVs documentation</a>.  

## 9. Debugging FreeFrame Plugins
If you have troubles getting your plugin to run or return useful data you may want to output debug information from different parts of your code. There is a systemwide debug-console which you can write messages to. Using the OutputDebugString() function and a code-construct like this:  
```c  
char buffer[100];  
sprintf(buffer, "%i x %i", FImageSize.width, FImageSize.height);  
OutputDebugString(buffer);
```  
allows you to send messages to that console. The <a href="http://technet.microsoft.com/en-us/sysinternals/bb896647.aspx" class="extURL" target="_blank">DebugView</a> application offers a window into that console. 