---
uid: 34087080-7498-4ea6-95f6-320f4bcf550a
---

# Capture Cards




Capture Cards either come with a WDM driver or a proprietary API. In the first case simply use the <span class="node"> VideoIn (DShow9)</span> to access them, in the second case you'll have to write your own [plugin](xref:766d8ac2-5145-417d-b2df-37d24e3b2b6f) in order to to implement the API.  

**Blackmagic Design DeckLink**  

* [DX11 BlackmagicDesign Decklink VideoIn](https://vvvv.org/store#dx11-blackmagicdesign-decklink-videoin) by <a href="http://nsynk.de/" class="extURL" target="_blank">NSYNK</a>  

**Legacy**  

For (legacy) analog capture cards based on a bt878 or compatible chip this common WDM driver is available:  
http://btwincap.sourceforge.net/  

**See also:**  
* [List of Capture Cards](xref:02abbea9-3a49-401d-bd74-aa89704b87b0#capture-cards)  



