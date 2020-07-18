---
uid: 33c7823e-87a2-4e01-b22e-1394db68a757
---

# Change Log - vvvv40beta18
released on 02 09 08  

## general
* new sub category 'Spreads Sets' with four new nodes (=, Intersect, Unify, Subtract), which treat spreads like sets -> order and multiplicity of elements is unimportant  
* CategoryNodelist is now sorted correctly  
* fixed a major bug: seems that all patches didn't evaluate correctly in the first frame. <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=21063&topics_threshold=0&topics_offset=7&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">link</a>  
* convverter (difff.xml) got a new feature: changing the default value of pins is possible from now on. the old default value is manually set by the convverter, if no other value for that pin was stored in the patch.  

## new nodes
* Substitute (Spreads) substitutes values. See wishlist <a href="http://www.vvvv.org/tiki-view_forum_thread.php?comments_parentId=19947&topics_threshold=0&topics_offset=14&topics_sort_mode=lastPost_desc&topics_find=&forumId=12" class="extURL" target="_blank">link</a>  
* = (Spreads Sets) returns 1 if all elements in input spreads are equal  
* Intersect (Spreads Sets) all elements of output spread must be at least once in each input spread. See whishlist <a href="http://www.vvvv.org/tiki-view_forum_thread.php?comments_parentId=10049&topics_threshold=0&topics_offset=142&topics_sort_mode=lastPost_desc&topics_find=&forumId=12" class="extURL" target="_blank">link</a>  
* Unify (Spreads Sets) unifies all input spreads to one output spread  
* Subtract (Spreads Sets) returns all elements of input spread 1 without elements of input spreads i (i > 1)  
* CDR and CAR for types string and color. See wishlist <a href="http://www.vvvv.org/tiki-view_forum_thread.php?comments_parentId=14566&topics_threshold=0&topics_offset=78&topics_sort_mode=lastPost_desc&topics_find=&forumId=12" class="extURL" target="_blank">link</a>  
* GetSpread for type string  
* InsertSlice for types string and color  
* Scale (DShow9 Meraka) scales directshow RGB24 video streams  
* Crop (DShow9 Meraka) crops directshow RGB24 video streams  
* SharedMemory (DShow9) pumps shared memory into a directshow stream  

## changed nodes
* Swap (Spreads).v4p replaced with native node  
* SetSlice/GetSlice (3d Vector).v4p replaced by SetSlice/GetSlice (Spreads) nodes and a default binsize of 3  
* Sift (Values) improved performance  
* Get- and SetSlice nodes enhanced by new input pin 'Bin Size'  
* GetSlice nodes enhanced by new output pin 'Output Bins'  
* Spectral nodes - if first bin size is negative remaining bin sizes won't be ignored anymore  
* Expr node now supports an arbitrary number of variables with user-defined names, better error handling  
* IOBox (Value Advanced) is now capable of evaluating mathematical expressions on user input  
* TypoSpread (Spreads) now has all inputs spreadable  

## fixed nodes
* MidiClock (Devices) works again  
* MidiTimeCode (Devices) works again  
* InsertSlice works correctly now  
* ScopeSpread (DShow9) stereo mode fixed  
* Counter (Animation): now it resets to the default value in the first frame and after that checks up/down pins to change values from there. <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=21063&topics_threshold=0&topics_offset=7&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">link</a>  
* receive nodes of all types: fixed bug reported here: <a href="http://www.vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=21184#threadId21203" class="extURL" target="_blank">link</a>  
* fixed ViewFrustumCulling (EX9.Geometry Mesh) bug: <a href="http://www.vvvv.org/tiki-view_forum_thread.php?comments_parentId=21166&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">link</a>  
* VideoIn (DShow9) should no longer freeze for random webcam models