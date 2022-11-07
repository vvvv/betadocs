---
uid: "contribution/dds-ring-buffer"
uid-meta: "contribution/dds-ring-buffer-meta"
comments: 
 items: 
  - uid: "87459"
  - uid: "87461"
  - uid: "87476"
  - uid: "87483"
  - uid: "87484"
  - uid: "87569"
  - uid: "87602"
  - uid: "87605"
  - uid: "87628"
  - uid: "87630"
uid-files: "contribution/dds-ring-buffer-files"
title: "DDS Ring Buffer"
contribution: "true"
---

<div class="box">
Note:
Currently hardcoded for DXT5
</div>

1.  Introduction
I know a few of you are streaming DDS's off the HDD to playback video. Here's a ring buffer to do that.


1.  Notes
* All file loading is performed in off-mainloop threads
* Pushing to GPU is performed on main thread (as required in DX9)
* TextureUtils provides a mechanism to create textures from files (e.g. DDS), we use this mechanism for the first frame
* Remaining frames with same resolution will be copied to GPU with an UpdateTexture function*
* Keeps persistent memory buffers between frames if the file sizes are the same (i.e. true of DDS)
(*) I've manually coded the UpdateTexture function to parse the DDS file header and contents, and push the contents to the GPU without recreating the texture

1.  DXT5 lookups are slow?
We didn't end up using this plugin, as we found that texture lookups became slower on DXT5 compared to X8R8G8B8 textures (hits the render stage).

I think in general this effect is negligible, but for the amount of texture lookups we're using (7 * HD in PS 3.0 on Radeon 6970's) it became a noticeable hit (dropped to 40fps min framerate vs 60-synced before). This effect continued after the texture was loaded (i.e. the slowdown was purely at render time). 

The hypothesis that a texture lookup on DXT5 takes more GPU time than from an X8R8G8B8 makes theoretical sense, but might turn out to be incorrect. However, it is in line with our tests here.