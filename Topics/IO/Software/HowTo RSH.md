---
uid: 669aa8be-27ac-4727-acb4-c66dbc20a1c4
---

#  RSH-HowTo
##  Aufbau eines RSH-Netzwerks mit v4

###  Abstract RSH in v4
* RSH ist ein tcp-basiertes Protokoll, mit dem auf einem Remote-Rechner Befehle ausgeführt werden können  
  * Ist mit einer Hostliste(.rhosts-datei) erweiterbar, auf der alle Rechner (name oder IP) vermerkt sind, die Befehle ausführen dürfen.  
  * Geht bis auf einzelne Befehle für einzelne Rechner  zu konfigurieren  
  * .rhosts ist auch abschaltbar  
  * RSH gilt als extrem unsicher, wird daher nicht mehr verwendet oder nur in genau abgeschirmten internen Netzwerken.  
* Auf den Rechnern, auf denen ein Programm ausgeführt werden soll muss der **RSH-Daemon** laufen  
* Der Rechner, der die Ausführung steuert wird als **RSH-Client** bezeichnet  
* Der **RSH-Client** ist als v4-Knoten implementiert  
* Der **RSH-Daemon** läuft als eigenständiges Programm auf den Remote-Rechnern (Written by Silviu C. Marghescu (http://www.cs.umd.edu/~silviu)).  

###  Setup
* Setup eines **RSH-Daemons** (Standalone)  
  * Das Programm **rshd.exe** (Written by Silviu C. Marghescu (http://www.cs.umd.edu/~silviu)) starten.  
  * Optionen -d (nicht als Dienst) -r(keine .rhosts-datei, Zugriff von jedem Host möglich  
  * **rshd -d -r**  
  * Anmerkung: Das Starten als Dienst (Nach erfolgreichem Installieren als Dienst mittels rshd.exe -install) funktioniert nicht bei xp und 2000.  

* Typischerweise  hat man einen vvvv-Server, von dem aus man zb. die vvvv-Clients starten möchte. Dies ist der **RSH-Client**.  
  * RSH-Knoten anlegen  

  * Input-Pins  
  * Spread mit anzusteuernden **RSH-Daemons**(Name oder IP) festlegen  
  * Spread mit Befehlen festlegen  
  * Befehle sind alles, was man über die DOS-Kommandozeile ausführen kann  
  * Execute-Spread zum Ausführen  
  * beim RSH-knoten handelt es sich um einen **ThreadedNetworkNode**, d.h. das Execute eines jeden Slices wird in einem eigenen Thread ausgeführt  
  * Alle Befehle geben irgendwann über den **RSH-Daemon** einen Wert zurück. Es gibt hierbei im vvvv**RSH-Client** keinen Timeout  
  * Bei interaktiven Programmen wie v4 kommt i.d.r. erst eine Rückgabe wenn das Programm beendet ist.  
  * Cancel-Spread zum Beenden  
  * Hiermit wird eine wartende Verbindung zum **RSH-Daemon** beendet.  
  * (ACHTUNG): Das Programm wird nicht beendet, nur die Verbindung. Dadurch ist es möglich, einen neuen Befehl an den entsprechenden **RSH-Daemon** abzuschicken  

  * Output-Pins  
  * ResultCode -1: Fehler, 0: wait, 1: ready bzw ok  
  * ResultValue: ausführlichere Beschreibung  

###  aktueller windows rsh daemon
* http://sourceforge.net/projects/rshd  
