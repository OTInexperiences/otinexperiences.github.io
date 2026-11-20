---
layout: page
title: Geometric Chuck
date: 2011-06-26 20:17:19 +0000
author: Alan
categories: []
tags: []
permalink: "/software/software-windows/geometric-chuck/"
original_url: http://ab48.uk/otblog/software/software-windows/geometric-chuck/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/software-windows/geometric-chuck/"
parent: "/software/software-windows/"
---
The standard mechanical geometric chuck comprises of several stages (about 20 is all thats physically possible) .  Each individual stage is connected to the previous stage (except the first stage which is connected to the main spindle). It is offset from the previous stage by some given amount, and is driven possibly as a different speed from the stage as its spindle  is attached to the spindle belonging to the previous stage through a small gear chain. A stage may be rotating in the same or opposite direction to the previous stage and this is dependant upon the number of gears connecting the two stages together.  An odd number of gears makes the stage rotate in the opposite direction to the previous one. An even number of gears ensures that it rotates in the same direction.

So the path of the spindle of each stage describes a circle around the centre of the spindle of the previous stage as it also rotates.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/ce66af0509-chuck-stage.png' | relative_url }}"><img alt="" class="size-medium wp-image-1050" height="298" src="{{ '/assets/recovered/dffc9b629d-chuck-stage-300x298.png' | relative_url }}" title="chuck-stage" width="300"/></a>
<figcaption>Single stage of geometric chuck</figcaption>
</figure>
<p style="text-align: center;">Multiple stages are connected together so that each one is offset from the previous stage</p>
Mostly computer implementations of a geometric chuck allow a very large number of stages but still keep with the mechanical original and only cater for stages having circular paths. However, as I am writing a software simulation of the chuck and therefore its stages are virtual and have no real physical constraints I could make each stage a more complex path.

So in the windows version of my program OTWorkbench I allow each stage of my geometric chuck to be described by a Rosette. This greatly increases the number of patterns that can be generated. Of course there are many more chances of ending up with a pattern that is artistically ugly but hey thats life.

Examples

This first example shows a single circular stage whose radius is 100mm

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"> <img alt="" class="size-medium wp-image-1054" height="192" src="/assets/placeholder-original-image.svg" title="Geochuck1" width="300"/></a>
<figcaption>Single circular stage</figcaption>
</figure>

Then we can add a second circular stage and set its radius to 50mm and its  spindle speed ratio to 2 : 3 and rotating in the opposite direction to the first stage.

<a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-medium wp-image-1053" height="175" src="/assets/placeholder-original-image.svg" title="Geochuck2" width="300"/></a>

Now change the second rosette and make it an ellipse whose Major radius is 80, keep the minor radius at 50 then we get.

<a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-medium wp-image-1055" height="179" src="/assets/placeholder-original-image.svg" title="Geochuck3" width="300"/></a>

Whilst not to attractive it does show the difference

Now finally change the first stage to an ellipse whose major radius is 100 but whose minor radius is 20

<a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-medium wp-image-1056" height="155" src="/assets/placeholder-original-image.svg" title="Geochuck4" width="300"/></a>

What happened there!!!

I need to find some more pleasing examples but I hope the images above give you some of the flavour of the types of path you can create.
