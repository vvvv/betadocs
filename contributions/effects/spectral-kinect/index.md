---
uid: "contribution/spectral-kinect"
uid-meta: "contribution/spectral-kinect-meta"
comments: 
 items: 
  - uid: "90600"
  - uid: "90604"
  - uid: "90613"
  - uid: "90693"
  - uid: "90705"
  - uid: "90723"
  - uid: "90790"
  - uid: "90793"
  - uid: "90900"
  - uid: "90905"
  - uid: "91082"
  - uid: "91507"
  - uid: "91508"
  - uid: "113467"
  - uid: "113493"
  - uid: "113706"
  - uid: "113743"
  - uid: "153483"
  - uid: "212005"
  - uid: "213043"
  - uid: "213048"
  - uid: "213600"
  - uid: "218471"
  - uid: "220440"
  - uid: "245500"
  - uid: "262783"
  - uid: "264378"
uid-files: "contribution/spectral-kinect-files"
title: "Spectral Kinect"
image: "Spectral Kinect.png"
contribution: "true"
---

Spectral Kinect is the result of heavy cooking with pixel shaders and particle system.

The recipe :

- Start by adding the [vux](http://vvvv.org/users/vux)'s Kinect Skeleton plugin.
- Add some Ciant Particles system by the mighty [Martin Zrcek](http://vvvv.org/users/Martin+Zrcek) and mix them together.
- Take some of [unc](http://vvvv.org/users/unc)'s texture FX(as usual), add them to the previous preparation and play with it.

Finally mix everything with lots of late nights experimenting, tweaking and fun using your favorite Multipurpose Toolkit and that's it !

You've got the Spectral Kinect !

The idea : if there is someone in front of the Kinect (sadely only one...) the spray/ball will transform into the Spectral and you can control it with your Kinect. 
Then, if there is nobody, the Spectral will transform back into the spray/ball and move around.

If you don't have a Kinect, you can toggle the default position to see how it looks anyway.

Research steps can be seen here : http://www.flickr.com/photos/cloneproduction/sets/72157631903128574/

Video is here : https://vimeo.com/52612788

I'd like to thanks a lot, all those guys who makes plugin and effects, because without them, it wouldn't be possible to do that with vvvv.

Big Up guys !

Edit by Newemka: SPECTRAL KINECT working with Open NI

Hello everyone, I've updated this patch to make it working with Open NI. The MS Kinect Skeleton Nodes gives more joints positions, with the OpenNi Skeleton nodes, wrists, ankles and waist position are missing. Then I had to re-order the Joints ID in the ResampleSkeleton module.
Thanks for the help of LeCloneur! 