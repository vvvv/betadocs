---
uid: 2fdc5b67-00a0-46a2-8073-cf2debee3c2b
---

#  Other considerations


##  tWVP or mul(tW,tVP)

tWVP will multiply your transform in CPU, using mul (tV,TVP) will do it in GPU.  

Once big difference is when you do it in CPU it's only once per model, whereas mul(tW,TVP) is once per vertex.  

So it's also situational (please note that pre transform hardly works in instancing scenario by the way, unless you do it in Compute Shader).  

But generally I just keep 2 versions of the shader and use the fastest one (if i run into perf issues, if not, I don't care ;)  

##  Clean up 

If you don't use color transform (or anything else, texture sampling probably being the most important), get rid of it, or do a version with/without it.  

Operations at pixel level can add up very quickly, so if you don't need them get rid of them (and it's so simple to have 2 versions of shader with/without texture that it should be in your toolkit).  
