---
uid: "contribution/mqtt-revamped"
uid-meta: "contribution/mqtt-revamped-meta"
comments: 
 items: 
  - uid: "268370"
  - uid: "268396"
uid-files: "contribution/mqtt-revamped-files"
title: "mqtt revamped"
contribution: "true"
---

based off the [mqtt sender and receiver](xref:contribution/mqtt-sender-receiver) plugins by [korriander](http://vvvv.org/users/korriander)
v1.1 rewriting initiated and sponsored by <http://meso.net>


this implementation comes in **two flavours**:
### MQTT (Network Client)
monolithic Client node - for simple applications:
a combined sender and receiver node (think rs232) since you most probably only specify the connection once

###  Client, Send and Receive
do the client connection in one place of the patch and pass the client to the places, where sending and receiving is actually happening


with following improvements:
#### v1.1:
* username and password
* (Clean) Session
* Keep Alive Period
* Last Will / Testament
* remove retained message
* improved overall stability

[source](https://github.com/woeishi/VVVV-MQTT) on github 
