---
uid: b5cb6815-294b-44ff-94cf-365b2e4d6a81
---

# HowTo Release a Pack
<a href="https://vvvv.org/contributions/7934/all" class="extURL" target="_blank">Packs</a> are topical collections of plugins/modules/effects. Here is how you create a pack for sharing it as a contribution.  

```
 PACKNAME\core (for managed .dlls)
 PACKNAME\core\x86 (for native 32bit .dlls)
 PACKNAME\core\x64 (for native 64bit .dlls)
 PACKNAME\factories
 PACKNAME\girlpower (for demo patches)
 PACKNAME\nodes*
 PACKNAME\nodes\effects (or \dx11, geom11, texture11 for DX11 effects)
 PACKNAME\nodes\modules
 PACKNAME\nodes\plugins
```

\* The `\nodes` directory should include a nodelist.xml as explained here: <span class="node">nodelist (vvvv)</span>.  

You can also set a version for your pack and create diffffs in case you want to change namings from one release to the next, see: <a href="https://vvvv.org/blog/patch-conversions-pack-versioning" class="extURL blog" target="_blank">Patch Conversions & Pack Versioning</a>  

And here is how to [use a Pack](xref:772e8696-25d4-4d8b-a31b-db4dd1ce1f3f#other-packs).  
