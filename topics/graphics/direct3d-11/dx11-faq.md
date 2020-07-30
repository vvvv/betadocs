---
uid: b1bb8d73-cbd5-44fd-b512-ec9086f9c2ed
---

# DX11 FAQ
Incoming...  

**table of contents**  


## Can i deal with DX9 and DX11 at the same time?
Generally it is possible to render with the old DX9 pipeline and new DX11 pipeline in the same patch.   

You just have to handle the rendered result over to the other pipeline as shared texture (see the modules <span class="node">DX9ToDX11 (DX11.Texture 2d)</span> in the dx11 pack or <a href="https://discourse.vvvv.org/t/As shared Texture, DX11-> DX9" class="extURL forum" target="_blank">As shared Texture, DX11-> DX9</a> for the other way round).   

But be aware that the performance might not be good, when both pipelines have to wait for eachother. Depending hardly on what you do, you migth have noticeable framedrops at random while <span class="node">PerfMeter (Debug)</span> tells you vvvv is only waiting for the mainloop! In some cases using [multiple instances of vvvv](xref:2eb3d2a2-d4c1-4bc0-bcd8-16e48d756b16#allowmultiple) can increase your framerate massively, as both pipelines then render asynchronously via an individual cpu thread.