---
uid: 511c5e9e-a4b0-4f82-914b-2231cea23cfe
---

# MultiBoygrouping
<span class="include">TODO INCLUDE boygroupingtoc</span>  

# Introduction


![](~/img/Multiboygrouping-65Projectors.png "")  
*Click to enlarge*   



Simply put, clients cannot only obey to one master but receive patches and values from any number of servers you want them to.   

#### Examples
* Imagine the following setup: You have <a href="http://www.checksum5.com/459/intro" class="extURL" target="_blank">65 projectors</a> showing one continuous visual, but also at times they are supposed to show special content in 5 clusters of around 12 projectors each. Here, instead of having one server that needs to compute all the patches of the master-visual and the individual area contents at once you can make use of MultiBoygrouping. Specify one master server that has all the clients connected and provides the master-visual and dedicate 5 area-servers to provide individual area contents that are only connected to the individual areas clients.   

* Also imagine a live collaborative event where you have some clients connected to projectors and multiple operators connected to them at the same time with their own server...  


# How to



Practically the only thing you need to do to assign a client to multiple servers, is starting it with additional /client commandline parameters, like:  
 /client 192.168.0.100 /client 192.168.0.200:5555
Note that here it is necessary to use a different port for every connection as described in the [FAQ](TODO INTERNALLINK:boygrouping#faq).  

>note:It is important to make sure all servers were started before any of the clients did startup. Otherwise the behavior maybe quite random.  



# Features

![](~/img/Boygrouping-Server1.png "")   
*Server1*  
![](~/img/Boygrouping-Server2.png "")   
*Server2*  


Using Send / Receive nodes on ***Server1*** and ***Server2*** respectively allows to transfer Layers or any other data of the [Node Datatype](TODO INTERNALLINK:patching-basics#data-types)!  

**How to do this**  
On *Server1* you want a boygrouped <span class="node">S (Node)</span>, on *Server2* you want a boygrouped <span class="node"> R (Node)</span>.  

1. Boygrouping S on *Server1* is easy. 
1. Now on *Server2* you create a S with the same SendString, but don't boygroup it. Like this you can select that SendString on the boygrouped R (on *Server2*). 

**See also:**  
* [MultiBoygrouping forum-thread](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=31271&topics_threshold=0&topics_offset=7&topics_sort_mode=lastPost_desc&topics_find=&forumId=7)  

