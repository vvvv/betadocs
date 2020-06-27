# Test Framework
In order to prevent certain bugs from resurfacing again after they've been fixed, vvvv has a test framework. The framework consists of a couple of nodes and a simple template that test-patches have to follow to test for a specific known bug. If the bug persists, the patch returns an error-, otherwise a success-code.   

Everytime the vvvv build-server creates a new [alpha-vvvversion](TODO INTERNALLINK:/downloads/alphas) it also runs all available test-patches. If any of the test-patches fails, the build is not being released and the devvvvs are being informed about the problem.  

Therefore the more test-patches we collect about known issues the less likely it is that our build-server lets a buggy build slip through. Here is how you can help us to improve the release-quality of vvvv by creating and sending us test-patches for issues you find:  

1. Create a test-patch by starting from "\lib\nodes\Template test.v4p" patch
1. Make sure the test fails
1. Upload the patch in the forum or pull-request to https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/tests/patches

## Test Patches
To be recognized as a test-patch by the build-server a patch needs to:  
* follow this naming scheme:  
  * "* test.v4p", e.g: "DuplicateNodes test.v4p" or "Cons (String) test.v4p"  
* have the following in- and outlets  
  * Inlets: Run (bang)  
  * Outlets: Success (bool), Message (string), Running (bool)  

![](~/img/Template2(Test)_2017.03.14-18.34.04_0.png "")  
*The template for test-patches*  

The test-framework will open every such patch and bang its <span class="pin">Run</span> input. Now the creator of the patch is responsible to test for a specific case and return a <span class="pin">Success</span> of 1 (for true) or 0 (for false). Additionally a <span class="pin">Message</span> can be returned. Typically it is enough to run tests for exactly one frame only and the <span class="pin">Run</span> input can be directly connected to the <span class="pin">Running</span> output. But it is also fine to have tests running for a couple of frames by setting <span class="pin">Running</span> back to 0 after some frames past.   

The build-logs including test-results per build-attempt can be found on the build-server:  
* <a href="http://vvvv.org:8111/viewType.html?buildTypeId=vvvv45_alpha_x64" class="extURL" target="_blank">for x64</a>  
* <a href="http://vvvv.org:8111/viewType.html?buildTypeId=vvvv45_alpha_x86" class="extURL" target="_blank">for x86</a>  

## Useful Nodes
The *Test* category in the nodebrowser holds a couple of nodes that can be useful for building test-patches, like:  
- Assert (Test)  
- AreEqual (Test Value)  
- AreEqual (Test String)  
Consult their help-patches to learn how to use them.  

## Test Rig
To run test-patches locally, get TeamCityTester.v4p from here:  
https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/tests  

and enter the directory that holds your test-patches into the Directory IOBox, then press Run Tests.  

This is the same patch our build-server runs, so the TTY output is a bit cryptic but you should be able to identify problems there.