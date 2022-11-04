---
uid: "contribution/basic-facebook-graph-api-dynamic-plugins"
uid-meta: "contribution/basic-facebook-graph-api-dynamic-plugins-meta"
comments: 
 items: 
  - uid: "73518"
  - uid: "73524"
  - uid: "104016"
  - uid: "104098"
  - uid: "105501"
  - uid: "111229"
  - uid: "112859"
  - uid: "191197"
  - uid: "191268"
uid-files: "contribution/basic-facebook-graph-api-dynamic-plugins-files"
title: "Basic Facebook Graph API Dynamic Plugins"
image: "Facebook_2011.12.17-15.16.36.png"
contribution: "true"
---

I have done some facebook graph api dynamic plugins that should not get burried on my hdd so i would like to share them here. These are my first attempts on c#, so the code may be bit clumsy, but beeing honest the important crucial parts are copy pasted anyway. A nice fact is, that you do not need any external facebook sdk.

These are five examples for talking with the facebook graph api from within vvvv:

-List a users albums.
-List an albums photos.
-Create new albums.
-Upload photos to an album. 
-Basic posts to a wall

All the hard work really is done by the WebClient class:
 
WebClient.DownloadDataAsync 
WebClient.UploadDataAsync
WebClient.UploadFileAsync

are really straight forward and easy to handle methods.

You can of course use these to call other graph api´s functions like:
Read the feed, comment something, like something, list friends ..and many others. You just have to provide the right URI and valid parameters for a particular api call.Find more details at facebook´s developer pages:
http://developers.facebook.com/docs/reference/api/

Notes:

Please mind that you will need a facebook developer account to be able to work with these plugins. This requires registering by mobile phone or creditcard number.

These plugins are meant to be used with an offline access token. There is no "on the fly" authentication but a helppatch is provided for getting started with a facebook app and access token stuff.

Thank you for helping me out in the forums on the plugin topics. Special thanks go to frank at frank-it-beratung.com who made wonderful and easy to follow tutorials on the webclient stuff and facebook communication. -> http://frank-it-beratung.com/blog/?s=facebook

Honorable mentions in dev: philip :)

####  **update:**
###  According to the Garph API changelog, 
###  these Plugins will expire on 30.04.2015
See: https://developers.facebook.com/docs/apps/changelog
They were written against the 1.0 Version of the API
