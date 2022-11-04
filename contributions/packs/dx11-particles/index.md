---
uid: "contribution/dx11.particles"
uid-meta: "contribution/dx11.particles-meta"
comments: 
 items: 
  - uid: "164848"
  - uid: "164991"
  - uid: "164992"
  - uid: "164993"
  - uid: "165058"
  - uid: "165061"
  - uid: "165259"
  - uid: "178128"
  - uid: "193947"
  - uid: "194255"
  - uid: "195251"
  - uid: "203440"
  - uid: "203441"
  - uid: "203452"
  - uid: "206483"
  - uid: "207213"
  - uid: "213023"
  - uid: "213095"
  - uid: "213098"
  - uid: "219077"
  - uid: "219086"
  - uid: "219097"
  - uid: "230944"
  - uid: "231009"
  - uid: "231029"
  - uid: "233963"
  - uid: "234648"
  - uid: "234808"
  - uid: "236517"
  - uid: "236539"
  - uid: "236552"
  - uid: "236553"
  - uid: "236564"
  - uid: "236565"
  - uid: "236567"
  - uid: "236568"
  - uid: "236569"
  - uid: "236570"
  - uid: "236572"
  - uid: "236579"
  - uid: "236612"
  - uid: "236616"
  - uid: "236631"
  - uid: "236633"
  - uid: "236647"
  - uid: "236683"
  - uid: "236689"
  - uid: "236725"
  - uid: "236760"
  - uid: "236761"
  - uid: "236763"
  - uid: "236806"
  - uid: "236855"
  - uid: "236983"
  - uid: "237020"
  - uid: "237022"
  - uid: "237030"
  - uid: "237032"
  - uid: "237035"
  - uid: "237386"
  - uid: "237387"
  - uid: "237389"
  - uid: "237411"
  - uid: "237412"
  - uid: "237475"
  - uid: "237480"
  - uid: "238325"
  - uid: "238329"
  - uid: "238683"
  - uid: "238684"
  - uid: "238687"
  - uid: "238707"
  - uid: "238708"
  - uid: "238709"
  - uid: "238748"
  - uid: "239166"
  - uid: "239172"
  - uid: "239179"
  - uid: "239194"
  - uid: "239209"
  - uid: "239242"
  - uid: "239245"
  - uid: "239276"
  - uid: "239277"
  - uid: "239288"
  - uid: "239332"
  - uid: "239333"
  - uid: "239336"
  - uid: "239425"
  - uid: "239442"
  - uid: "239444"
  - uid: "239971"
  - uid: "239975"
  - uid: "239976"
  - uid: "240001"
  - uid: "240681"
  - uid: "240684"
  - uid: "240686"
  - uid: "240689"
  - uid: "241338"
  - uid: "241342"
  - uid: "241442"
  - uid: "243834"
  - uid: "245805"
  - uid: "245856"
  - uid: "245857"
  - uid: "246870"
  - uid: "247234"
  - uid: "247381"
  - uid: "247822"
  - uid: "248703"
  - uid: "248706"
  - uid: "248708"
  - uid: "249666"
  - uid: "249867"
  - uid: "249932"
  - uid: "250155"
  - uid: "250195"
  - uid: "250252"
  - uid: "250363"
  - uid: "250521"
  - uid: "250734"
  - uid: "250735"
  - uid: "250742"
  - uid: "252735"
  - uid: "259451"
  - uid: "269917"
  - uid: "269946"
  - uid: "269947"
  - uid: "269959"
  - uid: "269972"
  - uid: "269975"
  - uid: "269976"
  - uid: "269978"
  - uid: "269980"
  - uid: "270892"
  - uid: "271580"
  - uid: "272907"
  - uid: "273734"
  - uid: "273747"
  - uid: "274109"
  - uid: "274508"
  - uid: "274754"
  - uid: "278784"
  - uid: "278799"
uid-files: "contribution/dx11.particles-files"
title: "DX11.Particles"
image: "particleslogo.png"
contribution: "true"
---

<div class="vimeo embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe title="vimeo-player" src="https://player.vimeo.com/video/206586772" width="640" height="360" frameborder="0" allowfullscreen></iframe>
</div>

This pack is a collection of tools and techniques to handle a lot of particles on the GPU.
It also includes tools for dealing with depth cameras like Kinect 1 or 2.

1.  features
* clean and modular design
* emit, select, modify and visualize particles
* very easy customization of particle attributes
* many different types of emitters, modifiers and selectors
* kinect calibration for mapping realworld data to the virtual scene
* hittest/count, centroid, bounds, peak, ...
* includes many additional plugins for vvvv ( for example dynamic shaders(!) and MultiBufferRenderer)

1.  releases
* current version: 1.0.6
* changelog: https://github.com/letmp/dx11-particles/blob/master/CHANGELOG.md

1.  getting started
**You need:**
* latest version of vvvv
* latest version of [directx11-nodes](xref:contribution/directx11-nodes)

**Installation:**
* The easiest way (to install the **latest version**) is to use [/contribution/VPM](/contribution/VPM). Use this link after you installed it: <vpms://raw.githubusercontent.com/vvvvpm/vpdb/master/tmp/dx11.particles/dx11.particles.1.0.0.vpack>

* Second way (to install the **latest version**) is to download https://github.com/letmp/dx11-particles/archive/master.zip You have to unpack it and copy "dx11-particles-master\packs\dx11.particles" to your packs folder. Then you have to go to "your-vvvv-dir\packs\dx11.particles\nodes\plugins\" and delete all subdirectories that don't apply to the architecture you are using.

* The third way (to install an **potentially outdated version**) is to download the zip file from this contribution page. Unpack the zip file and copy dx11-particles into your packs folder. Be sure to use correct architecture builds.

After installation you can see all nodes of this pack by typing dx11.particles in your node browser. There are help patches for all included nodes that give small examples how to use them.

1.  for developers
You can fork the project here: https://github.com/letmp/dx11-particles
I really appreciate all of your help to let this pack grow. It is quite easy to build new modifiers and selectors. So if you have something that should be part of the pack just get in contact via robert@intolight.de or create a pull request via github.

1.  bugs
Please report any bugs here: https://github.com/letmp/dx11-particles/issues

1.  license
© Robert Willner, 2018
Author: robert.willner@gmail.com

This software is distributed under the [CC Attribution-NonCommercial-ShareAlike 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license.
If you want to use this pack for a commercial project, please contact robert.willner@gmail.com and tell me about your project or your goal.

1.  >>> Please consider purchasing a license for commercial use! <<<
See [/store](https://store.vvvv.org/)
