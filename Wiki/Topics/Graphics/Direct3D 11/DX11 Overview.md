# DX11 Overview
**table of contents**  


## Introduction

DirectX 11 set of nodes allows to use latest features introduced in new graphics card. Beside new shader stages (tesselation been advertised more than enough), a lot of new interesting features are also now accessible (compute shaders/indirect drawing/stream out...)  

This totally replaces the DirectX 9 rendering, as it's a brand new set of nodes.  

Please note that there is still some features/nodes missing, but the beauty of it is... it's open source!!! So you are more than welcomed to contribute missing nodes ;)  

## Comparison over DX9 rendering

From DirectX10 the pipeline has changed drastically, a lot of obsolete features have been removed, and a set of new features has been introduced.  

Here is a small list of removed features:  
* No more fixed function, the pipeline is fully Shader based.  
* AlphaTest has disappeared , now you need to do it in shader  
* No more built in Mesh, you need to handle geometry yourself.  

New list of interesting features:  
* Compute shaders, fully integrated to the pipeline  
* Geometry instancing, allows to replicate the same geometry several times.  
* Indirect Draws: Allows the graphics card to command a draw call  
* Buffers: Allows to use more generic usage set of data  
* Lot of new ways to sample textures.  
* Texture Gather: Allows to save lot of sampling in some cases.  
* Many Many more... ))  


## Structural Changes

Those changes are more vvvv related, but moving to a new pipeline implies a few different things patching wise.  

* Default Blend mode is now Disabled, So Alpha will NOT work by default. Blend has a cost so you should enable it when you need it.  
* No more old fixed DX9 nodes (Sphere/Segment...)  
* System is very shader centric, so it's more than recommended to learn some HLSL ))  
