---
uid: 3de7e372-3e35-4e2c-83bd-be1898a02bac
---

# Lightstrive - an interactive light projection
As part of the <a href="http://www.athens2004.com/en/OlympicLookOfAthens" class="extURL" target="_blank">Catch the Light</a> program accompanying the olympic games in Athens in August 2004 we've been invited to realize one of the <a href="http://www.athens2004.com/en/OlympicLookofAthensInteractiveArtInstallations" class="extURL" target="_blank">9 installations</a> that have been setup throughout the city.  

The fassade of a building is illuminated by a virtual lightsource that can be played with like a ball thus creating different lighting for the fassade every moment.   


![](~/img/trapeza01.jpg "")   
![](~/img/trapeza02.jpg "")   
![](~/img/trapeza03.jpg "")   


![](~/img/trapeza04.jpg "")   
![](~/img/trapeza05.jpg "")   


# Team
* Michael Höpfel  
* Sebastian Gregor  
* joreg  
Additional credits go to Michael Mehling for last minute programming at meso, Michael Mehling and Jenny Michel for their help on setting up the hardware and to Adi and Marianna as our fabulous production team in Athens.  

Further documentation on:   
* <a href="http://www.hoepfel.net/?page_id=29" class="extURL" target="_blank">hoepfel.net</a>  
* <a href="http://www.checksum5.com/89/lightstrive" class="extURL" target="_blank">checksum5.com</a>  

# Movie 
{mov:[/tiki-download_file.php?fileId=15}](TODO INTERNALLINK:/tiki-download_file.php?fileId=15})  


 

# Making Of

Lightstrive is completely realized with our inhouse developed graphical programming language vvvv and runs on two standard windows pcs with current graphics hardware.   

The audience is being tracked by a low latency firewire camera mounted high above on the opposite building viewing the whole interactive zone of about 22m. Direction and power of the users movement is extracted by analysing the video over time. A resulting vector is used to update the lights/balls movement that is otherwise being calculated by a physics engine that also includes the facades geometry in its calculations. Therefore the light/ball can also be caught in one of fhe balconies in which case the game restarts.   

The lights/balls current coordinate is always sent to the second pc where it is used to calculate the correct shadows cast by the point-lightsource represented by the ball. Shadows are calculated via custom vertex- and pixelshaders.  

* the place, korai, the bank building by day  
* photos of setup  




#  Early Screenshots


the tracker system  

![](~/img/tracker.jpg "")   




the shadowing system  


![](~/img/lighstrivedesktop_3.jpg "")   




 


![](~/img/sidehousewireshadow_3.jpg "")   


















![](~/img/lighstriveshadowmapwire_4.jpg "")   


