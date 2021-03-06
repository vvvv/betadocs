---
uid: 78351a6a-f070-4cb4-9902-e376cb7dcd58
---

# change log - vvvv50beta35.8
released on 25 06 17  

## VVVV
* code completion in code editor working again (was broken since beta35) https://discourse.vvvv.org/t/code-editor-completion-broken-rc5/15273  
* fix: https://discourse.vvvv.org/t/cant-copy-paste-nodes-from-a-module/15297  

## VL
### general
* fixed crash when opening girlpower patches where Destroy operation was deleted  
* fixed crash when using process state output in Create operation  
* state output of empty record constructor was hidden  
* fixed crash when having type with multiple Update operations   
* fixed renaming of pins that are used in a pin group  

### ui features/changes/fixes
* fixed several bounds bugs (on copy paste / duplicate, moving and resizing elements, loading old documents)  
* select all works again https://discourse.vvvv.org/t/ctrl-a-to-select-everything-in-current-vl-patch/15290/3  
* menu entries which change the pin count will now be disabled in case they've no effect https://discourse.vvvv.org/t/increasing-decreasing-pin-count-via-right-click-menu/15287  
* value editor of pads keeps in sync with set type https://discourse.vvvv.org/t/cannot-not-enter-string-into-io-box-created-by-middle-click/15298  
* SolutionExplorer doesn't steal focus on navigation  
* SolutionExplorer doesn't expand selected item on navigation  
* IO box holds changes for 100ms in order to see all bangs  

### fixed nodes
* ToInt8 was in wrong category  
* Filename (Split) now returns filename correctly without extension  
* Filter (Animation) has 1 second as default time and got a Progress output pin  

### new nodes
* SetCount (Spreads)  

### experimental
* Interval (Multimedia Timer) reactive event source with millisecond precision  
* Interval (Busy Wait Timer) reactive event source with nanosecond precision, always uses 100% of one CPU core but shares that with the workload