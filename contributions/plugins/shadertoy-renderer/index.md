---
uid: "contribution/shadertoy-renderer"
uid-meta: "contribution/shadertoy-renderer-meta"
comments: 
 items: 
  - uid: "216991"
  - uid: "216992"
  - uid: "217001"
  - uid: "217002"
  - uid: "217007"
  - uid: "217025"
  - uid: "217032"
  - uid: "217034"
  - uid: "217047"
  - uid: "217052"
  - uid: "217117"
  - uid: "217119"
  - uid: "217120"
  - uid: "217149"
  - uid: "217151"
  - uid: "217175"
  - uid: "217179"
  - uid: "217182"
  - uid: "217236"
  - uid: "217880"
  - uid: "217881"
  - uid: "217916"
  - uid: "217935"
  - uid: "217950"
  - uid: "250816"
  - uid: "250967"
  - uid: "250976"
  - uid: "260333"
  - uid: "260970"
  - uid: "268198"
  - uid: "268240"
  - uid: "268247"
  - uid: "274856"
  - uid: "274939"
  - uid: "275231"
uid-files: "contribution/shadertoy-renderer-files"
title: "Shadertoy Renderer"
image: "Screen Shot 2016-02-20 at 23.56.09.png"
contribution: "true"
---

Rendering GLSL fragment shader with shadertoy syntax and output vvvv texture(dx11).

### shadertoy?
shadertoy is the web application to coding and sharing glsl fragment shader (pixel shader) using WebGL by Beautypi.
if you not familiar with shadertoy, see [https://www.shadertoy.com](https://www.shadertoy.com).

### how to use
just input shader code and play. shader input(uniforms) and main(void) function are managed in renderer node. you don't need write it.
other basic help, see [shadertoy howto](https://www.shadertoy.com/howto)

### input uniforms status
* vec3 iResolution: ok
* float iTime: ok (rename from iGlobalTime from v0.3)
* float iTimeDelta: ok (from v0.2)
* float iFrame: ok (from v0.2)
* float iChannelTime<4>: no
* vec4 iMouse: ok (fixed v0.2)
* vec4 iDate: ok (from v0.2)
* float iSampleRate: no
* vec3 iChannelResolution<4>: no
* samplerXX iChanneli: ok. use iChannel0,iChannel1,iChannel2,iChannel3

### change log
#### v0.3(22.09.2018)
* remove dx9 support
* rename iGlobalTime to iTime

#### v0.2(13.03.2016)
* dx11 support
* add & fix input uniforms
* multiple renderer support

### work in progress
* play even renderer hidden
* video input and movie as texture

### src
https://github.com/minoru-ito/ShadertoyRenderer

<div class="box">
Note:
no editor, Sound shader, VR shader.
</div>