---
uid: "contribution/textbox-(dx11)"
uid-meta: "contribution/textbox-(dx11)-meta"
comments: 
 items: 
  - uid: "236700"
  - uid: "236713"
uid-files: "contribution/textbox-(dx11)-files"
title: "Textbox (DX11)"
image: "Textbox (DX11) help-Renderer_2017.03.12-19.51.25.png"
contribution: "true"
---

I found DX11 text a bit hard to wrangle when making GUIs because text will resize when the renderer resizes.
So I made this hacky patch that undoes all of the text nodes internal logic and makes text live inside a quad transform regardless of renderer size or quad shape. 

Now spreadable! 
TransX bug fixed
 
Free/Open Source/Go Crazy
Made with DX11 v1.01 x64 
and vvvv50beta35.2_x64

Limitations: 
It works best in single line mode with short strings. There is a multi line mode but it's a bit unpredictable and will sometimes break its bounds. 
