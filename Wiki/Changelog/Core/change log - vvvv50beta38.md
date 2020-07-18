---
uid: eba683cd-2e27-47e9-b226-4f72b324bedf
---

# change log - vvvv50beta38
released on 20 11 18  

## VVVV
### general
--- fixed a problem with CreateNode in /shutup mode  

### plugin interface
--- indexing an empty spread will throw proper IndexOutOfRangeException - https://discourse.vvvv.org/t/have-a-more-descriptive-exception-when-trying-to-access-a-slice-of-an-empty-spread/16810  

## VL
### general
--- <a href="https://vvvv.org/blog/vvvv50beta38" class="extURL blog" target="_blank">new file format</a>! Can read patches saved with beta37 but not the other way round!  
--- IO boxes can store any kind of data for which a <a href="https://vvvv.org/blog/vl-serialization" class="extURL blog" target="_blank">serializer</a> is registered.  
--- use Ctrl+K to expose pins to Create/Split from selected pads  
--- fixed crash when pasting auto connected node into document patch   
--- fixed incorrect target code in if region in case condition input evaluated to false at compile time   
--- fixed compiler crash when accessing default value operations of types it didn't see through a patch itself (reported by @bildwerk and @chk via riot)  
--- fixed relative paths to directories not working  
--- fixed process using CreateDefault instead of Create for initialization - https://discourse.vvvv.org/t/vl-forward-process-node-create-vs-createdefault/16692  
--- fixed wrong target code when using any Count or Length properties of mutable collections  
--- fixed crash in backend when using delegate regions with unused pins  
--- when looking up referenced assemblies the current document folder and all its subfolders will recursively searched for. This should lead to a more stable assembly lookup as it less dependes on already loaded assemblies. It also removes the requirement to package everything up in a NuGet package.  
--- caching access on disk when resolving assemblies  
--- fixed race condition when creating symbol sources for assemblies   

### new nodes
--- IPs, IPs (Ethernet), IPs (Wifi) -> return IPv4 infos  
--- Ping -> pings an IP  
--- Executor -> shellexecute node  
--- Batteries -> returns PC battery infos  
--- Args -> returns commandline parameters  
--- ScreenShot node (experimental)  
--- Ellipsis nodes...  

### changed nodes
--- fixed Metronome  
--- fixed JSONReader (Reactive)  
--- Wanderer (2d) has better defaults now  
--- SplitToLines now works with all line-endings: CR, LF and CRLF  
--- fixed deserialization not working on classes  
--- fixed crash when serializing with FSPickler  
--- ToObservable nodes will now send the initial message to the first downstream subscribers in the first frame  
--- fixed experimental WebSocketServer node and added a help patch for it