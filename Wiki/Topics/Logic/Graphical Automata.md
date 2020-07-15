---
uid: 250959b9-c2b3-420e-ad36-0b7c6b784fb6
---

# Graphical Automata
>note:  
Check also: <a href="https://vvvv.org/contribution/automata-ui" class="extURL contribution" target="_blank">automata-ui</a> which is much more convenient.  
  

From now on you can easily design your very complex logical state machine for the <span class="node">Automata (Animation)</span> node with a graphical editor called <a href="http://qfsm.sourceforge.net/screenshots.html" class="extURL" target="_blank">Qfsm</a>. Stefan Duffner, the developer of Qfsm, kindly added an export window for vvvv automata code:  

![](~/img/automataexport_1.png "")  

Download Qfsm for windows here:  

<a href="http://sourceforge.net/projects/qfsm/" class="extURL" target="_blank">http://sourceforge.net/projects/qfsm/</a>  

To use it, simply create a new state machine with the following settings:  

![](~/img/qsfm_settings.png "")  

Then make some states an connect them with events (transitions). these transitions will be the input pins for the automata node. If you want a special output bang for a transition, enter a name in the 'output' field of the transition. if this field is empty a default output will be created named after the state to which it goes with the prefix 'Do'. enable in menu view->mealey outputs to see the outputs at the transitions as well.  

![](~/img/qsfm_settings_transition.png "")