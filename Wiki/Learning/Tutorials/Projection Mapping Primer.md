# Projection Mapping Primer
When talking <a href="http://en.wikipedia.org/wiki/Projection_mapping" class="extURL" target="_blank">Projection Mapping</a> you have to essentially distinguish between two different types. Depending on your prerequisites and desired visual effects you'll have to choose between:  


#  Homography Approach
If you only need to project flat content onto flat surfaces, ie  texturing some real-world flat geometry with some animated wallpaper, go for this simplest of approaches. It is named after <a href="http://en.wikipedia.org/wiki/Homography_%28computer_vision%29" class="extURL" target="_blank">the math behind it</a> and essentially allows you to throw an image onto a flat surface from an arbitrary projector-position as if it was thrown on the surface head-on.   

![](~/img/badMapperV3.jpg "")   
*badMapper*  

On OSX there is a software called <a href="http://www.madmapper.com/" class="extURL" target="_blank">MadMapper</a> that uses this appoach and lets you pipe any flat content through onto arbitrary flat real-world surfaces. In vvvv you have the <span class="node">Homography (Transform)</span> that would be the basis of any such mapping tool. See <a href="https://vvvv.org/contribution/badMapper" class="extURL contribution" target="_blank">badMapper</a> for an example that establishes a basic workflow.  

#  Re-Projection Approach
If you have a more arbitrary or even curved surface to project onto you need two things:  
1. a virtual copy of the surface/geometry you want to project onto
1. the projectors lens characteristics and its position/rotation in respect to the surface

ad 1) Regarding the virtual copy of the surface you can either:  
* create a model using a 3d-modelling software  
* use <a href="http://reconstructme.net/" class="extURL" target="_blank">ReconstructMe</a>   
* in vvvv use <span class="node">GridEditor (EX9)</span> or start from a <span class="node">Grid (EX9.Geometry)</span> and modify it using <span class="node">MeshEditor (EX9)</span>.  

ad 2) In order to get the projectors lens/position/rotation you have 3 options:  
* manual: take manual measurements of its position/rotation and look up the lens characteristics in its manual  
* semi-automatic: use CalibrateProjector (CV.Transform) from the <a href="https://vvvv.org/contribution/vvvv.packs.image" class="extURL contribution" target="_blank">Image Pack</a>. Check <a href="https://vvvv.org/contribution/calibrate-and-re-project" class="extURL contribution" target="_blank">this contribution</a> to see the workflow.  
* automatic: use a solution like <a href="https://vvvv.org/blog/bsm-auto-alignment-with-vvvv" class="extURL blog" target="_blank">BSM Auto Alignment</a>  

With those two things at hand you can now setup a scene to project a virtual copy of the geometry on its real counterpart. Now any visual effect that plays on the surface of the virtual geometry, like light/shadow/texture animations will seemingly be part of the real-world geometry.  

Examples of this approach are [Lightstrive](TODO INTERNALLINK:Lightstrive) and Pablo Valbuena's <a href="http://www.pablovalbuena.com/selectedwork/augmented-sculpture-v1/" class="extURL" target="_blank">Augmented Sculpture Series</a>.  

For the basic setup of a 360° projection on a cylindrical screen, including soft-edging, see: [small 360 degree setup.zip](TODO INTERNALLINK:/tiki-download_file.php?fileId=1698)  


- --   

# Further Reading: Achieving 3d-Illusion effects
One very popular thing with projection mappings is 3d-illusion kind of effects like seen in Pablo Valbuena's <a href="http://www.pablovalbuena.com/selectedwork/n-520437-e-041900" class="extURL" target="_blank">The Hague City Hall</a> projection or AntiVJ's <a href="http://blog.antivj.com/2008/nuit-blanche-bruxelles" class="extURL" target="_blank">Nuit Blanche Bruxelles projection</a>. It is to keep in mind though that these effects only work for the audience when they stand in the right spot because when creating the effect a perspective has to be chosen for which the illusion is created.   

So here is what you do:  
You capture the virtual scene from a position which corresponds to the desired position of the audience. Then from that same position project the captured image onto the virtual geometry. This results in a scene where your desired 3d-effects are now a flat texture on the surface of the virtual geometry. Once you have that you go with the Re-Projection Approach as mentioned above. 