---
uid: ea8efa0f-acbf-419f-83db-e54abdd66613
---

# Diplom graphical Web Server Programming
## Ergebnis
>note:  
Die Diplomarbeit gibt es hier zum [tiki-download_file.php?fileId=861|download].   
  


## Offizielle Beschreibung:
Bei VVVV ( sprich Vau Vier ) handelt es sich um eine graphische Programmiersprache, deren Kernmetapher ein Datenflussgraph aus Knoten und Kanten ist, der während der Laufzeit jederzeit über ein intuitives, graphisches Interface manipuliert werden kann. VVVV wird seit einigen Jahren äußerst erfolgreich im Bereich interaktive Installationen für Ausstellungen und Messen, Audio- und Videoproduktion, Datenvisualisierung und Experimente zur parametrischen Ästhetik eingesetzt.  
Beispiel für ein solches Multimedia-Projekt ist der Fifa-Fußball-Globus, ein Teil des begleitenden Kunst- und Kulturprogramms der Fifa WM 2006, der 3 Jahre durch die 12 WM-Städte Deutschlands tourt, um seinen Besuchern das Thema Fußballkultur auf emotionale spielerische Weise nahe zu bringen.  
VVVV ist in Delphi entwickelt und für nichtkommerziellen Einsatz lizenzfrei nutzbar. Weitere Informationen unter [http://vvvv.org].  

Ziel der Diplomarbeit ist es, zu überprüfen, inwieweit sich ein graphisch manipulierbarer Datenflussgraph dazu eignet, in intuitiver Weise komplexe Web-Server-Applikationen zu entwickeln.   
Ausgehend von den Recherche-Ergebnissen soll die Arbeit in einer exemplarischen Anwendung ihren Abschluss finden.  
Die Diplomarbeit wird in Zusammenarbeit mit David Brüll/Björn Schwarzer geschrieben.  
An einem Beispiel (ähnlich Fußball-Globus) sollen Möglichkeiten geschaffen werden, ein in VVVV realisiertes Programm ( einen sog. „Patch“ ) über externe Schnittstellen (exemplarisch das WWW) zu manipulieren.  
 
Es wird eine XML-Beschreibung einer Selektion eines Patches generiert. Daraus werden die In- und Output Werte der einzelnen Knoten der Auswahl ausgelesen. Aus diesen wiederum generiert ein HTTP-Server dynamisch HTML-Formulare, die die Manipulation dieser Werte ermöglichen. Die neuen Werte werden mittels des Servers wieder über XML an den Patch zurückgegeben.  
Die diesbezüglichen Vorgänge sollen für den Nutzer transparent ablaufen und weitestgehend durch ihn beeinflussbar sein.  

Für die Implementierung steht bereits ein umfassendes Framework zur Verfügung. Dieses Framework muss jedoch um weitere geeignete Knoten ergänzt werden, wobei der genaue Umfang der Implementierung noch festzulegen ist. Notwendig sind:  

* HTTP Server-Knoten   
Analyse der Anforderungen und der existierenden Knoten (HTTP Client-Knoten für HTTP/GET und HTTP/POST existieren bereits). Implementation des HTTP-Standards in verschiedenen Knoten.   
--- > Björn Schwarzer  

* Graphical String Parsing  
Analyse. Parsing von XML-Strukturen mittels Datenflussgraph. Transformation von XML-Strukturen. Generierung von XML und HTML Strukturen. Beispielhafte Implementation zur Generierung von Webformularen und der internen VVVV -XML-Messages.   
--- >David Brüll  

Subthemen als einzelne Knoten  
* Kommunikation mit SQL Datenbanken  
* Umrechnung von Bildern in Binärdaten und zurück  
* Generierung von PDFs  
* XML-RPC  
* XLST 

## Quellen

### Allgemein
* <a href="http://citeseer.ist.psu.edu" class="extURL" target="_blank">Citeseer</a>  
* <a href="http://dict.leo.org" class="extURL" target="_blank">Leo Dictionary</a>  
* <a href="http://de.wikipedia.org" class="extURL" target="_blank">Wikipedia de</a>  
* <a href="http://en.wikipedia.org" class="extURL" target="_blank">Wikipedia en</a>  

### HTTP
* <a href="http://www.jmarshall.com/easy/http/" class="extURL" target="_blank">HTTP Made Really Easy</a>  

### Delphi
* Allgemein  
  * <a href="http://docs.indyproject.org/" class="extURL" target="_blank">http://docs.indyproject.org/</a>  
  * <a href="http://www.delphi-forum.de/" class="extURL" target="_blank">http://www.delphi-forum.de/</a>  
  * <a href="http://www.dsdt.info/" class="extURL" target="_blank">http://www.dsdt.info/</a>  
  * <a href="http://www.howtodothings.com/ViewSubCategory.aspx?SubCategory=41&PageNumber=0" class="extURL" target="_blank">How to do Things in Delphi (Viele Helferlein)</a>  

* Delphi & WWW  
  * <a href="http://www.prestwood.com/community/delphi/info/delphi_web_servers.asp" class="extURL" target="_blank">Developing Web Servers with Delphi(Tutorial)</a>  
  * <a href="http://www.adug.org.au/PastMeetings/Presentations/GlennLawrenceFeb98/Default.html" class="extURL" target="_blank">Writing Server-side Web Applications in Delphi with CGI Expert</a>  

* Delphi & Web Services  
  * <a href="http://www.howtodothings.com/ViewArticle.aspx?Article=312" class="extURL" target="_blank">HTDTID -Web Services - Made Simple in Delphi 6 Part I</a>  
  * <a href="http://www.howtodothings.com/ViewArticle.aspx?Article=276" class="extURL" target="_blank">HTDTID -Web Services - Made Simple in Delphi 6 Part II</a>  

* Delphi & XML  
  * <a href="http://community.borland.com/article/0,1410,27106,00.html/" class="extURL" target="_blank">Using XML and XSLT with Delphi 5 and WebBroker</a>  
  * <a href="http://www.destructor.de/xmlparser/download.htm" class="extURL" target="_blank">Free XML Parser for Delphi</a>  
  * <a href="http://www.philo.de/xml/dom/index_de.shtml" class="extURL" target="_blank">Extended Document Object Model v.3.1.22</a>  
  * <a href="http://www.firstobject.com/dn_markdelphi.htm" class="extURL" target="_blank">CMarkup for Delphi</a>  
  * <a href="http://xml.defined.net/sax/expat/" class="extURL" target="_blank">Expat Wrapper and XML Processing Library</a>  


### Visuelles Programmieren
* Allgemein  
  * <a href="http://citeseer.ist.psu.edu/63891.html" class="extURL" target="_blank"> C. M. Holt - Comparing Visual and Textual Languages (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/narayanan97visual.html" class="extURL" target="_blank">N. Hari Narayanan, Roland Hübscher - VL Theory: Towards a Human-Computer Interaction Perspective (1997) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/whitley96visual.html" class="extURL" target="_blank">K. N. Whitley - VPL and the Empirical Evidence For and Against (1996) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/375325.html" class="extURL" target="_blank"> Alan F. Blackwell, et al. - Cognitive Factors in Programming with Diagrams (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/burnett99visual.html" class="extURL" target="_blank">Margaret M. Burnett - Visual Programming (1999) (citeseer)</a>  
  * <a href="http://www2-data.informatik.unibw-muenchen.de/Lectures/WT2001/VL/VL.html" class="extURL" target="_blank">Prof. Dr. Andy Schürr - Visuelle Programmiersprachen</a>  
  * <a href="http://www.schiffer.at/vp/html/index.html" class="extURL" target="_blank">Schiffer - VP Grundlagen und Einsatmöglichkeiten</a>  
  * <a href="http://citeseer.ist.psu.edu/405810.html" class="extURL" target="_blank">Dorian Gorgan - Visual Programming Techniques (citeseer)</a>  
  * <a href="http://rw4.cs.uni-sb.de/~kerren/lehre/seminar/ss99/2/Uebersicht.html" class="extURL" target="_blank">Konzepte visueller Programmiersysteme</a>  
  * <a href="http://www-sfb288.math.tu-berlin.de/~armin/study/stud.html" class="extURL" target="_blank">Modellierung von Abhängigkeitsgraphen</a>  
  * <a href="http://citeseer.ist.psu.edu/boshernitsan97visual.html" class="extURL" target="_blank"> Marat Boshernitsan, Michael Downes - Visual Programming Languages: A Survey (1997) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/burnett94classification.html" class="extURL" target="_blank">Margaret Burnett, Marla Baker - A Classification System for Visual Programming Languages (1994)  (citeseer)</a>  
  * <a href="http://web.engr.oregonstate.edu/~burnett/vpl.html" class="extURL" target="_blank">Visual Language Research Bibliography</a>  

* VP und WWW  
  * <a href="http://citeseer.ist.psu.edu/idini98programming.html" class="extURL" target="_blank"> Roberto Idini, Mauro Mosconi, M. Porta - Programming Web-Based Applications within a Data-Flow VL (1998) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/mosconi99visual.html" class="extURL" target="_blank"> Mauro Mosconi, Marco Porta - A Visual Approach to Internet Applications Development (1999) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/573237.html" class="extURL" target="_blank"> Kang Zhang, Mao Lin Huang - An Integrated Visual Framework for the Human-Web Interface (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/baumgartner03visual.html" class="extURL" target="_blank">Robert Baumgartner - Visual Programming of Web Data Aggregation Applications (2003) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/chung02reverse.html" class="extURL" target="_blank"> Christina Yip Chung, Michael Gertz - Reverse Engineering for Web Data: From Visual to Semantic Structures (2002) (citeseer)</a>  

* VP und XML  
  * <a href="http://citeseer.ist.psu.edu/erwig00visual.html" class="extURL" target="_blank">Martin Erwig - A Visual Language for XML (2000) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/zhang01visual.html" class="extURL" target="_blank"> Kang Zhang, Da-Qian Zhang, Yi Deng - A Visual Approach to XML Document Design and Transformation (2001) (citeseer)</a>  
  * <a href="http://citeseer.ist.psu.edu/erwig03xing.html" class="extURL" target="_blank">Martin Erwig - Xing: A Visual XML Query Language (2003) (citeseer)</a>  

* VP und Web Services  
  * <a href="http://www.iks.inf.ethz.ch/publications/bio03v.html" class="extURL" target="_blank">Visual Composition of Web Services</a>  

### Web Services
* <a href="http://de.wikipedia.org/wiki/Web_Service" class="extURL" target="_blank">Webservices - Einführung de</a>  
* <a href="http://en.wikipedia.org/wiki/Web_service" class="extURL" target="_blank">Webservices - Einführung en</a>  
* <a href="http://msdn.microsoft.com/webservices/webservices/understanding/default.aspx" class="extURL" target="_blank"> Unterstanding Webservices</a>  
* <a href="http://www-306.ibm.com/software/solutions/webservices/pdf/WSCA.pdf" class="extURL" target="_blank">Web Service Architekur</a>  

* SOAP  
  * <a href="http://www.w3schools.com/soap/default.asp" class="extURL" target="_blank">W3Schools- SOAP</a>  
  * <a href="http://de.wikipedia.org/wiki/Simple_Object_Access_Protocol" class="extURL" target="_blank">SOAP - Einführung</a>  
  * <a href="http://webservices.xml.com/pub/a/ws/2002/04/16/soap.html" class="extURL" target="_blank">SOAP - Vor- und Nachteile</a>  

* Rest  
  * <a href="http://www.oio.de/public/xml/rest-webservices.htm" class="extURL" target="_blank">REST Web Services -  Einführung</a>  
  * <a href="http://www.xmlmagazin.de/itr/online_artikel/show.php3?id=209&nodeid=69" class="extURL" target="_blank">Der ganze REST</a>  
  * <a href="http://www.int-x.org/lib/exe/fetch.php?cache=cache&media=uni%3Arest.pdf" class="extURL" target="_blank">Seminararbeit zu REST (pdf)</a>  
  * <a href="http://webservices.xml.com/pub/a/ws/2002/02/06/rest.html?page=1" class="extURL" target="_blank">REST - Second Genaratiion Webservices</a>  
  * <a href="http://webservices.xml.com/pub/a/ws/2002/02/20/rest.html?page=1" class="extURL" target="_blank">REST and the Real World</a>  
  * <a href="http://www.xml.com/pub/a/2004/12/01/restful-web.html" class="extURL" target="_blank">How to Create a REST Protocol</a>  
  * <a href="http://www.xml.com/pub/a/2004/08/11/rest.html" class="extURL" target="_blank">Implementing REST Web Services: Best Practices and Guidelines</a>  
  * <a href="http://hinchcliffe.org/archive/2005/04/05/192.aspx" class="extURL" target="_blank">Can REST be considered a web service?</a>  

* REST vs SOAP  
  * <a href="http://webservices.sys-con.com/read/79282.htm" class="extURL" target="_blank">REST vs. SOAP: The Battle of the Web Service Titans</a>  
  * <a href="http://hinchcliffe.org/archive/2005/04/27/201.aspx" class="extURL" target="_blank">It's all about real interoperability: REST vs. SOAP redux</a>  
  * <a href="http://hinchcliffe.org/archive/2005/02/12/171.aspx" class="extURL" target="_blank">The hidden battle between web services: REST versus SOAP</a>  
  * <a href="http://webservices.xml.com/pub/a/ws/2003/09/30/soa.html" class="extURL" target="_blank">Kurze Gegenüberstellung von REST und SOAP</a>  
  * <a href="http://www.bawsug.org/archives/000003.html" class="extURL" target="_blank">Linksammlung Rest vs. SOAP</a>  
  * <a href="http://www.petefreitag.com/item/431.cfm" class="extURL" target="_blank">Rest vs. SOAP</a>  

## [DiplomGTP.Konzeption](xref:56e0ccbb-8d0d-4889-ad40-3625e564c7d7)
## ((DiplomGTP.Quellen))