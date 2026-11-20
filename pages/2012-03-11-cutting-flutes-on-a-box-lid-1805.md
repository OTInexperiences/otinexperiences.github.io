---
layout: page
title: Cutting flutes on a box lid
date: 2012-03-11 14:15:44 +0000
author: Alan
categories: []
tags: []
permalink: "/software/g-code-examples/cutting-flutes-on-a-box-lid/"
original_url: http://ab48.uk/otblog/software/g-code-examples/cutting-flutes-on-a-box-lid/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/g-code-examples/cutting-flutes-on-a-box-lid/"
parent: "/software/g-code-examples/"
---
This is the gcode program I wrote to cut the flutes in the top shown below.

<a href="{{ '/assets/recovered/e931f96a8a-top21.png' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1806" height="225" src="{{ '/assets/recovered/c2b8ac4400-top21-300x225.png' | relative_url }}" title="top2" width="300"/></a>You need to start by roughly shaping the top  to the following sloping section. The depth of the slope was about 8mm for the pattern above.

<a href="{{ '/assets/recovered/3926feffe9-top2.png' | relative_url }}"><img alt="" class="aligncenter size-full wp-image-1795" height="98" src="{{ '/assets/recovered/3926feffe9-top2.png' | relative_url }}" title="top2" width="200"/></a>To make the top above I made one cut of 0.5mm depth followed by a finishing cut of 0.1mm depth which I got by editing the data for depth passes and running the program again.
<h2>Program Code</h2>
down load listing  <a href="http://www.ab48.uk/otblog/wp-content/uploads/2012/03/fluting_code.txt">fluting_code</a> (rename to a .ngc file for emc)
<pre>(Example cut a simple scalloped top for a box    )
(Units are in mm )
(The V axis is the depth of cut, change to suit your setup )
(The B axis is the rotation axis, change to suit your setup)
(The Y axis is the pumping axis, change to suit your setup )
(The X axis is the traverse axis )
G21 G40 G49 G54 G80 G90 G94

#&lt;_safeheight&gt;     = 5

(************ main program *********)

(data for depth passes )
#&lt;curr_depth&gt;   = 0.0    (start cutting at this depth)
#&lt;max_depth&gt;    = -0.5   (deepest cut of pattern )
#&lt;depth_inc&gt;    = -0.5   ( ammount you want to take each pass )

(data for angle passes )
#&lt;angle_inc&gt;    = 15    (angle increment)
#&lt;angle&gt;        = 0     ( angle to index to)
#&lt;angle_max&gt;    = 360   ( last angle to index to)
#&lt;angle_twist&gt;  = 20    (angle to twist around)
#&lt;feedrate&gt;     = 50    ( feed rate )

(data for radial passes )
#&lt;outer_r&gt;  = 66    (71mm largest or outer radius )
#&lt;inner_r&gt;  = 5     (10mm smallest or inner radius)
#&lt;min_y&gt;    = 0
#&lt;max_y&gt;    = 10    (Max ammount to compensate for slope)

g90 g0 v[#&lt;_safeheight&gt;] y [#&lt;min_y&gt;]
o&lt;depthloop&gt; while [#&lt;curr_depth&gt; GE #&lt;max_depth&gt;]
        #&lt;angle&gt;=0
        o&lt;patloop&gt; while [#&lt;angle&gt; LT #&lt;angle_max&gt; ]
             g0 V[#&lt;_safeheight&gt;] Y[#&lt;min_y&gt;]
            X [#&lt;inner_r&gt;] B[#&lt;angle&gt;]
            g1 V [#&lt;curr_depth&gt;] f [#&lt;feedrate&gt;]
            X [#&lt;outer_r&gt;] Y[#&lt;max_y&gt;] B[#&lt;angle&gt; + #&lt;angle_twist&gt;]
            #&lt;angle&gt; = [#&lt;angle&gt; + #&lt;angle_inc&gt;]
        o&lt;patloop&gt; endwhile
        #&lt;curr_depth&gt; = [#&lt;curr_depth&gt; + #&lt;depth_inc&gt;]
o&lt;depthloop&gt; endwhile

M2</pre>
<h3>Notes</h3>
<ol>
<li>The value of <strong>angle_inc</strong> determines the number of flutes on the top. Here a value of 15 degrees gives 360 / 15  or  24 flutes.</li>
<li>The value of <strong>angle_twist</strong> determines the ammount of bend in the flutes. If angle-twist was zero the flutes would be straight. In the top above I make angle-twist the same as angle_inc so that the bend was equivalent to one flute position.</li>
<li>Set the <strong>feedrate</strong> dependant on type of wood etc.</li>
<li><strong>Outer_r</strong> and <strong>Inner_r</strong> depend upon the size of the top.</li>
<li>The program cuts the top starting at the centre and cutting outward.</li>
<li>The value of <strong>min_y</strong> would usually be zero as this point corresponds to the top surface of the piece.</li>
<li>If value of <strong>max_y</strong> was equal to the depth of the slope then a cut would be of equal depth down the slope. If max_y was greater than the depth of the slope, the cut would increase in depth as the cutter moved towards the outside of the piece because the work would be positioned nearer to it (by the difference between the depth of the slope and the value of max_y).  Conversley if max_y was less than the depth of the slope then the cut would become shallower as the cutter approached the outer radius of the piece.</li>
</ol>
In the piece above I made max_y greater than the depth of the slope by a couple of mm, and set the value of Outer_r to be a few mm larger than the outer radius of the piece itself.
<h3>Emc pre-plot</h3>
<a href="{{ '/assets/recovered/76b13b3480-EMc-preplot.png' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1807" height="300" src="{{ '/assets/recovered/a964bd7aaa-EMc-preplot-292x300.png' | relative_url }}" title="EMc-preplot" width="292"/></a>
