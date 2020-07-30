---
uid: e4204794-86c3-4980-b575-3a439cc53d77
---

# Change Log - vvvv50beta39
released on 18 11 19  

## general
* simplified installation via Installer  
* renamed setup.exe to config.exe (running it is only required if installer was not used)  
* now requires .NET 4.7.2  
* new documents are by default now saved to User\Documents\vvvv\beta(-preview)\Sketches  
* "Recent Patches" is a new entry in the main menu  
* vvvv.exe, config.exe as well as new installer are signed now  
* vvvv beta and gamma follow the same version format for example "vvvv beta 39" or "vvvv gamma 2019.1"  

## new nodes
* Rabbit (RCP), Stick (RCP), Carrot (RCP) for support of <a href="https://rabbitcontrol.github.io/" class="extURL" target="_blank">RabbitControl</a>  
* WebSocket (Network Client)  
* Euler (Get) get euler angles from a quaternion  
* Euler (Get Vector) get euler angles as vector from a quaternion  

## fixed nodes
* MP3Parser node can now cope with unicode infos  

## vl
<a href="https://vvvv.org/blog/vvvv-gamma-2019.1-preview#changelog" class="extURL blog" target="_blank">vl changes</a>