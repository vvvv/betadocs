---
uid: "contribution/automata-ui"
uid-meta: "contribution/automata-ui-meta"
comments: 
 items: 
  - uid: "226030"
  - uid: "226033"
  - uid: "226034"
  - uid: "226036"
  - uid: "226037"
  - uid: "226038"
  - uid: "226041"
  - uid: "226042"
  - uid: "226043"
  - uid: "226044"
  - uid: "226047"
  - uid: "226048"
  - uid: "226059"
  - uid: "226063"
  - uid: "226415"
  - uid: "226480"
  - uid: "226578"
  - uid: "227829"
  - uid: "227897"
  - uid: "227905"
  - uid: "227907"
  - uid: "227908"
  - uid: "227912"
  - uid: "227942"
  - uid: "228001"
  - uid: "228121"
  - uid: "228143"
  - uid: "228167"
  - uid: "229377"
  - uid: "229533"
  - uid: "232289"
  - uid: "237472"
  - uid: "237927"
  - uid: "237938"
  - uid: "237957"
  - uid: "239083"
  - uid: "239084"
  - uid: "239088"
  - uid: "239409"
  - uid: "239410"
  - uid: "239412"
  - uid: "239614"
  - uid: "241300"
  - uid: "241331"
  - uid: "243354"
  - uid: "243520"
  - uid: "243640"
  - uid: "243651"
  - uid: "243960"
  - uid: "245339"
  - uid: "248235"
  - uid: "248253"
  - uid: "248267"
  - uid: "248288"
  - uid: "248474"
  - uid: "248477"
  - uid: "248490"
  - uid: "248491"
  - uid: "248960"
  - uid: "248975"
  - uid: "249142"
  - uid: "249158"
  - uid: "249183"
  - uid: "249184"
  - uid: "249189"
  - uid: "249191"
  - uid: "249226"
  - uid: "249228"
  - uid: "249233"
  - uid: "249238"
  - uid: "249243"
  - uid: "249244"
  - uid: "249249"
  - uid: "249270"
  - uid: "249310"
  - uid: "260443"
  - uid: "260523"
  - uid: "260577"
  - uid: "261015"
  - uid: "261045"
  - uid: "261046"
  - uid: "274518"
uid-files: "contribution/automata-ui-files"
title: "Automata UI"
image: "automata1.9.png"
contribution: "true"
---

1.  Hello Automata UI !
this is a visual finite state machine editor with built in finite state machine.

You want bulletproof logic ? You better use the automata node! Well, that's what [bjoern" "bjoern](http://vvvv.org/users/bjoern%22+%22bjoern) told me a couple of years ago. And he was right. If your patch becomes more and more complex, more and more bugs turn up due monoflop, delay, flipflop and framedelay madness. It's much easier with a statemachine.   

But since it is probably no fun writing quadruples, it makes sense to introduce a visual editor. 

**Some Features**

So here it is. Inspired by bjoern's "Timer" concept, transitions not only last a frame but can have a configurable duration. Quite useful for any animated user interface project, where animated transitions should be in sync with your logic.

Transitions can be pingpong, meaning they can be bi-directional. States on the other hand have a duration as well, blocking any outgoing Transition for a certain amount of time.

More rules are in the help patch.

**Remarks**

And let's not forget, Automata UI is inspired by http://qfsm.sourceforge.net/.


we (wirmachenbunt studio) use the plugin in all recent projects and it made our vvvv patcher life a lot more pleasant. hence we hope it can help you too.

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/I8CmERSoyPc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

**CHANGELOG**

1.9
*Regions aka "the big OR" (Quote:Tonfilm)
*Auto uppercase statenames
*Autonaming for transtions
*Dialogs appear close to mouse

<div class="vimeo embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe title="vimeo-player" src="https://player.vimeo.com/video/278362310" width="640" height="360" frameborder="0" allowfullscreen></iframe>
</div>

1.8.3
*Help Patches
*new Spreadcount Behaviour
*comes as a pack
*new ResetToState Node
*improved enum handling
*set transition time fix


1.7.22
*new SetTransitionTime Node
*new TriggerTransition Node

1.7
*HiDPI compatible
*GetState node for easy animation
*Logging node for statistics
*spreaded automata UI
*CTRL + click on transition/state triggers them
*hidden focus pin to bring the UI up
*bezier transitions
*license key technique added

1.1
* spreadable edition
* view slice of automata in editor via inspektor setting
* force state by ctrl + leftclick on state
* removed JSON library dependency
* output all transition time settings as a spread  

----------------------------------------------------------------------------------

The plugin is open source
https://github.com/wirmachenbunt/AutomataUI