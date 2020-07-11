---
uid: 51377b2d-17a4-4b5f-b0c1-eb2cc11fe251
---

# VVVV SDK
The vvvv-sdk is the one-stop solution that allows you to contribute stuff to the [addonpack](TODO INTERNALLINK:About the Addonpack). It includes all of vvvv's open source code and the source code of all contributed addons. As it comes as a <a href="http://git-scm.com/" class="extURL" target="_blank">git</a> repository it allows you to conveniently stay uptodate with latest developments and always build your addons against the latest [alpha builds](TODO INTERNALLINK:/downloads/alphas).   

If you just want to browse through the code you can do so at the <a href="https://github.com/vvvv/vvvv-sdk" class="extURL" target="_blank">vvvv-sdk github page</a>. There are 3 reasons that would make you want to follow the instructions below:  
* you want to improve help patches/modules/effects/freeframes/plugins  
* you want to contribute your [addons](TODO INTERNALLINK:About Addons) to the [addonpack](TODO INTERNALLINK:About the Addonpack)  
* you're a h4kc0r  

>note:  
Note that for simple [dynamic plugins](TODO INTERNALLINK:dynamic plugins), effects or modules development you don't need the following.  
  

The following steps will get you going:  
## Install git
There are countless ways to work with git repositories on windows. In order to keep this guide clean we recommend using the <a href="http://code.google.com/p/gitextensions/" class="extURL" target="_blank">Git Extensions</a> GUI which served us very well. During its installation make sure to check installing all 3:   
* MsysGit  
* KDiff3  
* Windows Credential Store  
The first is the actual git engine (to which Git Extensions is only the GUI) and the second is a nice diff tool that helps you compare files when it comes to merge-conflicts. The third is useful helper that stores your login information in the windows credential manager. When asked to choose between OpenSSH and PuTTY just click Next.   

When running Git Extensions for the first time you'll have to enter your name and email address that will be used for your commits. Just follow the instructions there..  

If at some point you need/want to know more about working with git your best starting point is the <a href="http://git-scm.com/" class="extURL" target="_blank">official git website</a> with all its documentation and reference material.   

## Fork vvvv-sdk on github
The vvvv-sdk git repository is hosted on [http://github.com] (which is just one of many git-repository hosting services). In order to be able to contribute back to that repository one day you'll have to fork it. Here are the steps to do so:  
* create a free account on <a href="http://github.com" class="extURL" target="_blank">github</a>  
* navigate to https://github.com/vvvv/vvvv-sdk and press the fork button (top right!).   
* if interested <a href="http://help.github.com/fork-a-repo/" class="extURL" target="_blank">read more about forking on github</a>  

## Clone your fork to your local disk
Now on github you have your own "forked" version of the vvvv-sdk repository which you'll be mainly working with. Clone this repository to your local disk using Git Extensions like so:  
* click: Clone Repository  
* Repository to clone: https://github.com/YOUR_GITHUB_USERNAME/vvvv-sdk  
* Destination: specify a directory on your disk (eg. C:\dev\vvvv-sdk)  
* click: Clone  

This will take a while as it now makes a local copy (ie. clone) of the specified repository.  

## The repository layout
By cloning the repository you got a local copy that should look like this:  
> 
 \common
 \Hoster
 \scripts
 \tools
 \vvvv45
  

Now don't worry about \common \Hoster and \scripts and navigate to the \vvvv45 directory. What you see here is essentially the same directory layout you get when downloading vvvv as an enduser (except the \src and \tests directories which are not in the enduser download).   
> 
 \addonpack
 \girlpower
 \lib
 \licenses
 \src
 \tests
  

Navigate to the \addonpack directory which is where you will work. It contains 4 directories as follows:  
> 
 \girlpower
 \lib
 \licenses
 \src
  

The \src directory contains addons that need to be compiled before being useful (ie. plugins) while the \lib directory contains addons that will be shippped in the pack as they are (ie. modules, effects).  

So depending on what kind of addon you're working on you put your nodes in the respective subdirectories:  
> 
 \src\nodes\plugins 
 \lib\nodes\effects
 \lib\nodes\modules
  

## Build Core and Addonpack
Before being able to build the solution you'll need to download a matching vvvv.exe to the \vvvv45 directory. To do this make sure you've <a href="http://www.microsoft.com/en-us/download/details.aspx?id=34595" class="extURL" target="_blank">powershell 3.0</a> installed (installed by default on windows 8), open Git Extensions and go to the Menu  
 Git -> Git bash (Ctrl + G)
to open the bash. In the bash navigate to the directory you cloned to, eg:  
 cd /c/dev/vvvv-sdk
then type  
 scripts/fetch-binaries x86

At this point you'll need either the free <a href="https://www.visualstudio.com/products/visual-studio-community-vs" class="extURL" target="_blank">Visual Studio Community 2015</a> OR <a href="http://www.icsharpcode.net/OpenSource/SD" class="extURL" target="_blank">SharpDevelop 5</a> (SD5) including  the <a href="http://go.microsoft.com/fwlink/?LinkId=528261" class="extURL" target="_blank">.NET 4.6 targeting pack</a>, the <a href="https://www.microsoft.com/en-us/download/details.aspx?id=48159" class="extURL" target="_blank">Microsoft Build Tools 2015</a> and the <a href="http://msdn.microsoft.com/en-US/windows/desktop/bg162891" class="extURL" target="_blank">Windows 8.1 SDK</a>.  

Before running vvvv.exe from your \vvvv45 directory (which is the latest available alpha build of vvvvs closed sources) you need to build the opensource parts, including the whole addonpack so you have all the plugins from the pack available while working from this setup.   

The addonpack is split into 2 solutions:  
* \vvvv45\addonpack\src\Addonpack.sln  
* \vvvv45\addonpack\src\AddonpackCPP.sln  
The first of which contains managed plugins only (which is the biggest part of the addonpack) and is likely to compile without any issues.  

The second one contains mixed managed/unmanaged plugins that can only be built on a machine having the <a href="http://www.microsoft.com/en-us/download/details.aspx?id=8279" class="extURL" target="_blank">Windows SDK 7.1</a> installed.  

### Using Visual Studio 2015
* open Addonpack.sln  
* make sure: Build -> Configuration Manager -> Active Build Platform is set to *x86*  
* build it (F7)  

### Using SharpDevelop 5
* open Addonpack.sln  
* make sure: Build -> Set Platform is set to *x86*  
* update nugets: Project -> Restore Packages  
* build it (F8)  

Building may take a while and is supposed to return with "Build Successfull. 0 Errors" in which case you're done and can close the solution. If the build fails, you best [contact us on irc](TODO INTERNALLINK:howto use irc).  

## Integrate your plugins to the Addonpack.sln
Now you're ready to work on your own code. For this open the Addonpack.sln and add your project. Now in order to get your project built from within that solution you need to do one step manually:  
* open your project file with a text editor  
* insert the following line:  
  <Import Project="..\..\Default.Plugin.Project.settings" />
* remove all the conditional property groups:  
  <PropertyGroup Condition="...">...</PropertyGroup>

You can have a look at the project file of another plugin in the addonpack for an example of how your project file should look like.  

### Managed Dependencies
If your project has thirdparty .dll dependencies put them in a directory called  
 \dependencies
in your project directory and reference them from there.   

If your project depends on platform dependent assemblies put them in  
 \dependencies\x86
 \dependencies\x64
open the project file with a text editor and write something like this:  
  <Reference Include="AssemblyName">
    <HintPath>dependencies\$(Platform)\AssemblyName.dll</HintPath>
  </Reference>

### Unmanaged Dependencies
If your project references unmanaged .dlls you also put them in your local   
 \dependencies\PLATFORM 
directory but instead of adding them as reference to your project (which is not possible) you do as follows:  
* enable the "Show All Files" icon in the solution explorer  
* right click the newly shown up dependencies folder in your project and select the "Include in project" entry  
* select all the native dependencies, right click and select Properties  
* in the properties set *Copy to ouptut directory* to *Copy if newer*.   
This only needs to be done for such linked native .dlls since for ordinary references *Local copy = true* is the default anyway.  
When you compile your project you'll see that those native dependencies will get copied to the output directory including their relative path name. In order to be found at runtime we need to add this relative path name to the PATH environment variable once our plugin gets loaded. To do that add a static constructor to your plugin and put in the following lines of code:  
```  
public class MyPlugin ...  
{  
  // Static constructor
  static MyPlugin
  {
    var platform = IntPtr.Size == 4 ? "x86" : "x64";
    var pathToThisAssembly = Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location);
    var pathToBinFolder = Path.Combine(pathToThisAssembly, "dependencies", platform);
    var envPath = Environment.GetEnvironmentVariable("PATH");
    envPath = string.Format("{0};{1}", envPath, pathToBinFolder);
    Environment.SetEnvironmentVariable("PATH", envPath);
  }
}  

```  

### License
Place a file called   
 license-MYPLUG.txt 
directly in the directory of your plugin. From there it will be automatically collected and put in the common \addonpack\licenses directory after the build.   

### Helppatch
Don't forget to provide a helppatch for your plugin. Put helppatches directly into the  
 \addonpack\lib\nodes\plugins
directory. This is a bit of a mess, we know. Please come complain on [irc](TODO INTERNALLINK:howto use irc).  

## Update your clone of the vvvv-sdk
The git *pull* command is used to fetch (and merge) code from a remote repository. By default when you pull in your repository you'll update your local code from your remote code. But in order to get the freshest bits from the vvvv-sdk you need to pull from the original repository.   

For this you have to add the original repo as an extra *remote* to your repository. In the Git Extensions menu go to:  
 Remotes -> Manage remote repositories
and add a new remote giving it the name "upstream" and the url:  
> 
 https://github.com/vvvv/vvvv-sdk.git
  

Now you can pull from either of your two remotes:  
* origin: the remote repo of your fork on github  
* upstream: the remote repo of the official vvvv-sdk.   

Pulling upstream will get you the latest changes to the vvvv-sdk. Now in order to get the latest suitable vvvv.exe and setup.exe from a git bash call:   
 scripts/fetch-binaries

And whenever you do so make sure to rebuild the Addonpack.sln in order for the vvvv.exe you got to be compatible with the latest codechanges.   

>note:  
Like this you can also add even more remotes, eg. of other people's vvvv-sdk forks. Like this you can test changes those people made to their fork before they were incorporated into the official sources.   
  

## Contribute your stuff to the vvvv-sdk
You added a project to the addonpack and want it to be distributed with the official addonpack download? Send us a <a href="https://help.github.com/articles/using-pull-requests" class="extURL" target="_blank">pull request</a> pulling against the vvvv-sdk develop branch.   

vvvv is following <a href="http://nvie.com/posts/a-successful-git-branching-model/" class="extURL" target="_blank">this branching model</a>.  

Note that you can start multiple individual pull requests by creating different branches on your end and then pull-request from those against vvvv-sdk's develop branch.   

Before start a pull-request please make sure to:  
* follow [Conventions.CodingStyle](TODO INTERNALLINK:Conventions.CodingStyle) and [Conventions.NodeAndPinNaming](TODO INTERNALLINK:Conventions.NodeAndPinNaming)  
* not include too much stuff in one request (ie. always separate features from fixes)  

## 64bit builds
>note:  
Building the solutions as 64bit only works with Visual Studio 2015 for now since SharpDevelop 5 still ignores some settings in the Addonpack.sln and fails.   
  

When building the pack as 64bit you'll also need the according 64bit alpha of vvvv.exe which you can get by manually calling:  
 scripts/fetch-binaries x64
from the bash (remember: Ctrl+G in GitExtensions).