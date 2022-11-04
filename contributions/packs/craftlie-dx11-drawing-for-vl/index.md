---
uid: "contribution/craftlie-dx11-drawing-for-vl"
uid-meta: "contribution/craftlie-dx11-drawing-for-vl-meta"
comments: 
 items: 
  - uid: "241224"
  - uid: "241279"
  - uid: "241281"
  - uid: "241381"
  - uid: "241388"
  - uid: "243296"
  - uid: "243297"
  - uid: "244097"
  - uid: "244292"
  - uid: "247131"
  - uid: "247134"
  - uid: "247158"
  - uid: "247197"
  - uid: "247259"
  - uid: "248234"
  - uid: "249379"
  - uid: "249385"
  - uid: "272533"
  - uid: "273663"
  - uid: "274466"
  - uid: "274471"
uid-files: "contribution/craftlie-dx11-drawing-for-vl-files"
title: "CraftLie: DX11 drawing for VL"
image: "01_Overview-Renderer_2017.06.16-19.47.45.png"
contribution: "true"
---

The nodes resemble the beloved vvvv drawing nodes and will make you feel at home immediately. CraftLie creates a list of draw descriptions and sends them over one output pin to vvvv. In vvvv a special node takes the descriptions and renders them into a Renderer (DX11) of your choice.

No output pin mayhem and much better performance if you want to render complex scenes from VL.

![](https://vvvv.org/sites/default/files/imagecache/large/images/https://discourse.vvvv.org/uploads/default/original/2X/f/faccf63bf727ae06ecbaef14c3a7ad52c803569b.png)

Placing the drawing nodes inside your VL data types makes much cleaner patches and shows the joy of object oriented patching. This makes it perfectly suited for UIs and other drawing tasks that have complicated visual structures and need dynamic instances.

####  Customization
Keep in mind that the rendering still takes place in vvvv. So you can use your vvvv shader knowledge to customize the Renderer (Craftlie) and draw the shapes in a different style. It's also possible to output many layers from VL and draw each with a different custom Renderer (CraftLie).

####  What does CraftLie mean?
CraftLie is, like [FeralTic](https://github.com/mrvux/FeralTic) the dx11 library it is based on, and anagram of the major dx11 developer @flateric. Due to the fake nature of the drawing, the name fits perfectly.

##  Features
- Hierarchical layer system like in vvvv
- Layer can be transformed
- Layer can be put into world, view or projection space
- All basic primitives
- Simple text
- 3D Text
- Arbitrary Mesh Join
- Billboard sprites
- Textures can use relative paths to the vvvv patch that contains the Renderer (CraftLie)

##  Example Patches
Check the folder CraftLie.1.x.x\vvvv\girlpower for:
1. An overview patch which shows all nodes in action
2. How to use instancing
3. Interactive particle patch by @sebl
4. CPU core race which stresses all cores using [reactive nodes](/blog/vl-reactive-programming)
5. Sprites particles in perlin force field
6. Dynamic UI demo that creates layered windows
![Windows VL](https://vvvv.org/sites/default/files/imagecache/large/images/https://discourse.vvvv.org/uploads/default/original/2X/e/e91e8b34d6b80aaa246d08f0e82cb7061899f477.gif)

![Dynamic Particles](https://vvvv.org/sites/default/files/imagecache/large/images/https://discourse.vvvv.org/uploads/default/original/2X/8/8560baee876b0d3b66e37a511ad5d5c75454ad4d.gif) 

##  Installation
The pack works for both 32-bit and 64-bit alike.
0. Make sure you have [vvvv beta 35.7](https://vvvv.org/downloads) or newer
1. Install [latest dx11 pack](xref:contribution/directx11-nodes).
2. Put the folder in the zip into the vvvv packs folder e.g.:
 vvvv50beta38.1\packs\CraftLie.1.2.0

###  Source Code
<https://github.com/tebjan/CraftLie>