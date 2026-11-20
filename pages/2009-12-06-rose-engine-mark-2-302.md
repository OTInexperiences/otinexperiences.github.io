---
layout: page
title: Rose Engine Mark 2
date: 2009-12-06 17:08:15 +0000
author: Alan
categories: []
tags: []
permalink: "/rose-engine-mark-2/"
original_url: http://ab48.uk/otblog/rose-engine-mark-2/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/rose-engine-mark-2/"
---
I decided to design and build a stepper motor driven rose engine that was separate from my wood lathe.  The machine is now finished along with a cutting frame, various cutters and an overhead drive assembly.

<a href="{{ '/assets/recovered/53b06ef891-IMG_0068.jpg' | relative_url }}"><img alt="My completed CNC based rose engine" class="aligncenter size-full wp-image-1822" height="474" src="{{ '/assets/recovered/53b06ef891-IMG_0068.jpg' | relative_url }}" title="IMG_0068" width="640"/></a>

The image above shows the chuck from my plain wood turning lathe mounted on the rose engine holding a platter that I have turned on the wood lathe. This is how I intend to work, I will turn a bowl, box etc on my plain lathe then transfer the chuck to my Rose engine without the need to remove the work from the chuck. The cutting frame is held in a mount that will also hold a drilling frame and a Proxxon milling head.

The cutting frame is powered by a 0.5 hp 3phase motor controlled through a variable speed inverter. The maximum motor speed is 1500 rpm and the reduction between the pulley on the motor and the pulley on the cutting frame is 4 : 1. This gives my cutting frame a maximum speed of 6000 rpm.
<p style="text-align: left;"><a href="{{ '/assets/recovered/6492c29349-IMG_0124.jpg' | relative_url }}"><img alt="" class="aligncenter wp-image-1824" height="394" src="{{ '/assets/recovered/6492c29349-IMG_0124.jpg' | relative_url }}" title="IMG_0124" width="563"/></a>
To give some idea of scale the platter in the first photograph is about 350mm or 13.75inches  in diameter. I hope to be able to work on items up to 18 inches diameter which is the capacity of my plain turning lathe.</p>
<h2 style="text-align: left;">Axes</h2>
My rose engine is currently capable of movement along four axes.

The headstock which holds the workpiece has 3 degrees of movement.
<ol>
<li>Rotation around the main spindle</li>
<li>A transverse movement at 90 degrees to the spindle.</li>
<li>A movement along the direction of the spindle itself.</li>
</ol>
Thus the whilst the workpiece rotates it can move from side to side and forwards and backwards.

Currently the cutting frame is mounted on a slide that has one degree of movement that will move the cutting frame towards or away from the workpiece. The slide can be manually placed at any angle to the work.

<a href="{{ '/assets/recovered/abc9a4a845-Directions-150x1501.png' | relative_url }}"><img alt="" class="aligncenter size-full wp-image-1706" height="150" src="{{ '/assets/recovered/abc9a4a845-Directions-150x1501.png' | relative_url }}" title="Directions-150x150" width="150"/></a>I currently label these axes in a non standard way.
<ol>
<li>The axis along the main spindle is standardly the Z axis and the rotation axis around this is the C axis.  I label the spindle axis the Y axis and consequently its rotational axis is B.</li>
<li>The transverse axis is the X axis which is standard.</li>
<li>The cutter depth axis is either V or U depenant upon the orientation of the tool either towards or perpendicular to the spindle.</li>
</ol>
I do this because the emc axis which I use only has a 2D lathe mode (and I need 3D)  and the mill mode assumes that the spindle axis is vertical, wheras I want it to be horizontal. My axis allocation is no where near perfect but it gives me a view that is  more representative of my rose engine. If emc axis is ever changed to allow Z to be horizontal then I will revert to the standard axis notation.
<h2>Further Work</h2>
I want to rebuild the tool station to allow independent movement in all 3 dimensions, that is along X,Y and Z together with a rotation around the vertical Y axis.
<h2>Other Photographs of early stages in the build</h2>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="View of machine using the milling head" class="size-full wp-image-449" height="498" src="/assets/placeholder-original-image.svg" title="img_0045-1 (Modified)" width="690"/></a>
<figcaption>Using the milling head</figcaption>
</figure>

Unlike a standard rose engine which relies upon rosettes to determine the movement along each axis,. My machine is built mainly using linear bearings and ball screws connected to stepper motors. I will rely on a CNC controller (in my case emc2) running gcode to determine the movement along each axis.

I use three stepper motors; one to rotate the spindle holding the chuck (this is around the Z axis) , the second to move the spindle head horizontally (this is the X axis) and the third to move the spindle head forwards and backwards (along the Z axis). So you see there is no movement in the Y direction so this is a two axis machine.

The  tool post is able to be positioned so that the cutter is either cutting into the face of the work (along Z axis) or into the side of the work (along X axis).  The cutting frame will be held stationary and the work will be moved into the tool. The tool post can be raised and lowered slightly by turning the brass collar, this is how slight height adjustments are made.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="View of tool post" class="size-full wp-image-447" height="493" src="/assets/placeholder-original-image.svg" title="img_0044 (Modified)" width="673"/></a>
<figcaption>Tool post holding my home made cutting frame</figcaption>
</figure>

The stepper motor on the headstock  is connected to the shaft through a 16:1 gearbox which is keyed onto the shaft.  The shaft itself  is 20mm diameter and runs through two bearings one in each block and  is fixed at the motor end by a threaded brass nut tightening against a thrust bearing.  There is also another thrust bearing at the other end of the shaft held against the bearing block by the spindle end pushing against a brass sleeve.  I also added a brass sleeve between the two bearing blocks for decorative effect!! The spindle end is threaded M33 x 3.5  to match my wood lathe and was cut for rose version 1 (by a fellow member of my wood turning club - thanks Pete,  as I didn't have a metal screw cutting lathe at the time).

The other stepper motors are connected directly onto a ball screw using an oldham coupling just visible on the rear stepper in the image below.

The headstock is made from 4" x 1" aluminum and the shafts and linear bearings are 20mm diameter which I am reusing. The sliders are 1.5" x 1" aluminum bar bored to take the 20mm shafting, a sealed bearing and a thrust bearing both 12mm bore for the drive screw. The ball screw is 16mm diameter and runs through a ball nut which is bolted onto the headstock. Overall the headstock has a horizontal movement of around 300mm so if the headstock is moved over to one side and the tool post to the opposite side. I should be able to machine a pattern on bowls / platters up to 16 - 18  inches in diameter.

The steppers, 20mm rail and linear bearings and ball screw were cannibalized from previous projects, everything else was bought or made  specifically for this machine.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-425" height="456" src="/assets/placeholder-original-image.svg" title="img_0012" width="608"/></a>
<figcaption>Rear view of headstock</figcaption>
</figure>

The headstock is mounted on a pair of rails which are 16mm diameter using four linear bearings. This allows the headstock to move backwards and forwards using a second ball screw shown above. The two rails are clamped to 1 inch by 1.5 inch aluminum pieces which are 400mm long.  For anyone wondering about the mixed units,  I worked totally in metric but bought the Aluminum section in Imperial sizes off ebay. For anyone in the UK  I got all the rectangular section from<a href="http://stores.shop.ebay.co.uk/Forward-Metals-Ltd__W0QQ_armrsZ1"> Forward Metals Ltd</a>. I found them reliable with an excellent delivery service.

The image below is a view of the underside of my machine showing how the ball nut driving the forward-backward motion is fixed to a strap that lies across the sliding head.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-428" height="532" src="/assets/placeholder-original-image.svg" title="img_0021" width="710"/></a>
<figcaption>Underside of the machine</figcaption>
</figure>

The image below shows my unfinished  ornamental lathe placed alongside my plain wood turning lathe.  Also you can see the aluminum plate that will form the basis of my tool post. This plate will also run on linear bearings but will have clamps to enable it to be held rigidly at a given position (now complete ).

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-430" height="486" src="/assets/placeholder-original-image.svg" title="img_0025 (Modified)" width="638"/></a>
<figcaption>A view showing my new ornamental lathe with my plain woodturning lathe</figcaption>
</figure>

Now all I need is somewhere to put this new machine, I need another shed!!!
<h2></h2>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-456" height="398" src="/assets/placeholder-original-image.svg" title="img_0051 (Modified)" width="661"/></a>
<figcaption>View from the rear of the machine</figcaption>
</figure>

<a href="/assets/placeholder-original-image.svg"><img alt="View of machine" class="alignnone size-full wp-image-442" height="515" src="/assets/placeholder-original-image.svg" title="img_0040-1 (Modified)" width="601"/></a>
<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-454" height="426" src="/assets/placeholder-original-image.svg" title="img_0049" width="568"/></a>
