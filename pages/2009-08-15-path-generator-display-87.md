---
layout: page
title: Path Generator Display
date: 2009-08-15 17:52:24 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/rose-engine-project-2/path-generator-display/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/rose-engine-project-2/path-generator-display/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/rose-engine-project-2/path-generator-display/"
parent: "/software/ornamental-turning-workbench/rose-engine-project-2/"
---
This panel allows you to generate either a single path or multiple paths. You can enter relevant data such a start angle etc. The Rose engine path generator produces a path as a list of cylindrical coordinates. Each coordinate gives the radius, angle and depth of a point on the path.  These values are dependent on the position of the cutting tool.

<img alt="pathgenerator" class="alignnone size-full wp-image-104" height="581" src="/assets/placeholder-original-image.svg" title="pathgenerator" width="533"/>

You can alter
<ul>
<li>The starting angle as an angle between zero and 360 degrees.</li>
<li>The finishing angle either in degrees or number of rotations.</li>
<li>The angle increment which is the angular value between vertices  on the path.</li>
<li>The phase angle of each path.  Using this you can generate the same path several times but offset its position each time.</li>
</ul>
There is also a Repeater section which allows you to repeat a path generation many times.
<h3>Example</h3>
If you set the starting angle to zero  and the end angle to 360 the path generator will produce 361 points along the path determined by the headstock and the tool position.  Set the phase from zero to 60 and the number of repeat steps to 3. Pressing execute will generate three similar paths each varying in phase by 20 degrees.

<figure class="wp-recovered-caption">
<img alt="Repeating a simple path three times with a 20 degree phase change between each path" class="size-full wp-image-105" height="512" src="/assets/placeholder-original-image.svg" title="threepaths" width="505"/>
<figcaption>Repeating a simple path three times with a 20 degree phase change between each path</figcaption>
</figure>
