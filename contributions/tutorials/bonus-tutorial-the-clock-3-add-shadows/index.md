---
uid: "contribution/bonus-tutorial-the-clock-3-add-shadows"
uid-meta: "contribution/bonus-tutorial-the-clock-3-add-shadows-meta"
comments: 
 items: 
  - uid: "108113"
uid-files: "contribution/bonus-tutorial-the-clock-3-add-shadows-files"
title: "Bonus Tutorial: The Clock 3, Add Shadows"
image: "v4clock_2.png"
contribution: "true"
---

In the final part of this Clock project, I will show you how to use a Texture Filture effect to add some shadows to our clock hands. I will show you how to make a texture out off a renderer with transparency.

To be able to use the Shadow filter, be sure you have installed the Addon pack.

The Trick is to give your renderer some transparency, using a setalpha (color) and setting the texture format pin, in Herr Inspector to a format that supports alpha, like A8R8G8B8.

Also be sure to set the backbuffer width and height to the correct size, otherwise you image might look ugly.

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/3Rg8ZKg8wcI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>