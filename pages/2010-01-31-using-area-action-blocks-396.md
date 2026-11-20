---
layout: page
title: Using Area Action Blocks
date: 2010-01-31 16:30:59 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/paths/using-area-action-blocks/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/paths/using-area-action-blocks/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/paths/using-area-action-blocks/"
parent: "/software/ornamental-turning-workbench/paths/"
---
OTWorkbench allows you to specify a series of <strong>Action Points</strong> on a path  and  add an <strong>Action Block </strong>to the path.  The action in the action block is replicated at each action point along the path. If the block is an AreaActionBlock then the path is considered to be an area defined to be another area replicated and centered at each action point
<h3>Clock face example</h3>
If you wanted to machine a clock face and leave 12 empty areas for numbers to be added later. You would first create a Polygonal path with 12 vertices at a suitable radius for the numerals.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-520" height="388" src="/assets/placeholder-original-image.svg" title="clockface1" width="359"/></a>
<figcaption>Polygon with 12 sides</figcaption>
</figure>

Now instead of manually setting each point to be an action point we can apply an action rule to mark each point automatically. Select the path, right click

<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-521" height="196" src="/assets/placeholder-original-image.svg" title="clockface2" width="454"/></a>

Choose Action Rule &gt; Create Rule &gt; Index Rule &gt; All Points.

The chosen rule should be applied automatically. As seen above there are options to remove a rule or re-apply it.

You can use the display options in project information to set the colour of the action points and their relative size.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-522" height="435" src="/assets/placeholder-original-image.svg" title="clockface3" width="428"/></a>
<figcaption>Action point is hilighted in purple</figcaption>
</figure>

Next decide upon the shape of area to use lets say a circle radius 50 so create that area and set it to a MASK.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-523" height="453" src="/assets/placeholder-original-image.svg" title="Clockface4" width="445"/></a>
<figcaption>Mask area shown in pink</figcaption>
</figure>

Now finally we can add an area action block, and select our area from a list of possible candidates.

<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-524" height="209" src="/assets/placeholder-original-image.svg" title="Clockface5" width="427"/></a>
<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-525" height="141" src="/assets/placeholder-original-image.svg" title="clockface6" width="268"/></a>

The result is shown below.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-526" height="442" src="/assets/placeholder-original-image.svg" title="clockface7" width="436"/></a>
<figcaption>Ooops the circle is too big</figcaption>
</figure>

Now we can see that our circle is too big. So lets adjust it. Select the area outer boundary and change the radius value from 50 to 30 using the property explorer

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-527" height="450" src="/assets/placeholder-original-image.svg" title="clockface8" width="433"/></a>
<figcaption>Thats a better size</figcaption>
</figure>

Now you can go and create all the other paths that make up the face design, than apply the area to those paths. I have created another 40 wave paths

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-528" height="450" src="/assets/placeholder-original-image.svg" title="clockface10" width="473"/></a>
<figcaption>Areas have been applied</figcaption>
</figure>

Showing all the points on an example as above can be quite cluttered but the area around one action point shows as below.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-529" height="646" src="/assets/placeholder-original-image.svg" title="clockface11" width="540"/></a>
<figcaption>Detail around one action point</figcaption>
</figure>

Finally the G code is generated and loaded into emc whose preview is shown below

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-530" height="595" src="/assets/placeholder-original-image.svg" title="clockface12" width="720"/></a>
<figcaption>Preview image taken from emc</figcaption>
</figure>
