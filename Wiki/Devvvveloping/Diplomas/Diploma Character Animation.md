---
uid: 08c4bbdc-2cf5-4e9f-b190-285853981271
---

# Diploma Character Animation


# The idea

The aim of this thesis is to design a framework for vvvv, which enables developers to deal with character animation including skinning, skeletons, etc., easily.  

It should be determined, whether it is possible to transfer character animation specific terms and workflows from animation packages (e.g. Maya) into vvvv - and of course implement a possible solution in a set of vvvv nodes.  

While one common case of using character animation in vvvv might be importing a character rig from an external source using e.g. the [Collada Importer](xref:c9f8e059-dcf9-4712-a877-a200b17d7f76), this diploma should also find ways to create character rigs inside of vvvv dynamically.   

# Current State

The result is a set of 10 nodes implemented using vvvv's C# plugin interface:  

* CreateJoint (Skeleton)  
* Joint (Skeleton Join)  
* SetJoint (Skeleton)  
* GetJoint (Skeleton)  
* GetJointTransform (Skeleton)  
* SelectJoint (Skeleton GUI)  
* InputMorph (Skeleton)  
* MixPose (Skeleton)  
* AutoSkinWeights (Skeleton)  
* SkinDeformer (Skeleton)  

Watch <a href="http://vimeo.com/11739587" class="extURL" target="_blank">THIS VIDEO ON VIMEO</a> to see a quick compilation of some results which evolved while playing arount with those nodes.  

# Download

The developed nodes are now available for download: <a href="http://sagishi.zive.at/vvvvwiki/Skeleton.zip" class="extURL" target="_blank">Skeleton.zip</a>. Just place the files contained in the zip into the plugins-directory of you VVVV folder. Remember, that you need Microsoft .NET Framework 2.0 and SlimDX installed, to use the nodes.  

Alternatively, you can checkout the latest version of the sourcecode from the VVVV plugin repository on Sourceforge:  

*https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/addonpack/src/nodes/plugins/Skeleton/SkeletonNodes*  
and  
*https://github.com/vvvv/vvvv-sdk/tree/develop/common/src/core/Utils/Skeleton*  

# Tutorials

There are two articles about how to use those skeleton nodes here on the VVVViki, as well as on www.quasipartikel.at:  

* [a previous tutorial](xref:4c4a36ab-7a01-45dc-a4f9-9ed88c319918)  
* [skinning tutorial](xref:435355ec-58d2-4381-8e1f-a2b5821cb18e)  

# Known Issues

There are still a lot of issues with the nodes described above. I set up quick bug tracker at <a href="http://www.zauner900.net/bugs/index.php" class="extURL" target="_blank">www.zauner900.net/bugs/index.php</a>, where there are listed upcoming tasks to do. It's public, so feel free to add issues, if you want to give feedback. However, some of the major issues are:  

* **Constraints (or joint limits):** In the initial implementation there has been a way of setting constraints for each joint, to define, how far, and aroun which axes a joint can move. However, this has been in combination with saving joint rotations as euler angles. In the meantime, those euler angles have been replaced with quaternions. I haven't stumbled upon a simple way of defining limits for quaternion rotations - any hints very much appreciated.  

* **Performance:** There's definitly a lot of potential in improving performance. When several *InputMorph (Skeleton)* nodes are connected in serial, framerate drops. This is caused by the fact, that the whole chain of nodes has to recalculate complete skeletons, as soon es only one joint changes. There is need of a smarter way to handle this.  

* **Inverse kinematcis** would be awesome.  

* **Automatic computation of skinning data:** Besides being very slow, *AutoSkinWeights (Skeleton)* only performs rigid skinning, which results in un-smooth deformation in joint regions. This might be ok for prototyping and in the cases, the result should look noisy anyway. But for more advanced projects, *AutoSkinWeights (Skeleton)* should also provide a soft skinning algorithm. Using *heat maps* as proposed in section 4 of <a href="http://www.mit.edu/~ibaran/autorig/" class="extURL" target="_blank">Automatic Rigging and Animation of 3D characters</a> looks promising.