---
layout: page
title: Cutting spirals
date: 2011-06-22 18:14:18 +0000
author: Alan
categories: []
tags: []
permalink: "/software/g-code-examples/cutting-spirals/"
original_url: http://ab48.uk/otblog/software/g-code-examples/cutting-spirals/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/g-code-examples/cutting-spirals/"
parent: "/software/g-code-examples/"
---
Of course a helix is just a spiral and if we change our g code so that the spiral moves along the X axis simply by editing our program and changing the movement along the Y axis to  be along the X axis we can cut something like the image shown below.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/37a2ab8d31-IMG_0266.jpg' | relative_url }}"><img alt="" class="size-medium wp-image-1039" height="300" src="{{ '/assets/recovered/c4d3a989f1-IMG_0266-300x300.jpg' | relative_url }}" title="IMG_0266" width="300"/></a>
<figcaption>Inside of a box lid</figcaption>
</figure>

Here 5 spirals are cut into a box lid. The cutter was 5mm half round and rotating in the vertical plane. The spiral was started 10mm from the centre and cut 1mm deep into the wood. When the pattern was complete it was I filled with gold wax to hilight it then sprayed with an acrylic finish.  I like the way the starts of the spirals form a pentagon around the centre of the piece. The hollow in the centre was cut by advancing the cutter to -1mm and then rotating through 360 degrees.
<pre>(Author Alan Battersby)
(Program to cut a Spiral along the X axis as given by my machine setup)

(Comment - Note this is not for a standard Mill. )
(In my setup the cutter depth axis V may be set at any angle to the helix axial axis which is Y.)
(Also the helix rotates around the Y axis, here I use C but I suppose it should)

(set some global values )
G21 G40 G49 G54 G80 G90 G94
#&lt;_safeheight&gt; =2
#&lt;_feedrate&gt; = 100
#&lt;_traverserate&gt; =400

o&lt;helix&gt; sub
 #&lt;pitch&gt;  = #1  (pitch of helix )
 #&lt;length&gt; = #2  (length of helix to cut - width of cutter)
 #&lt;step&gt;   = #3  (angular step )
 #&lt;depth&gt;  = #4  (depth to cut )

 (first caluculate some required values for local variables)
 #&lt;max_angle&gt; = [ 360 * [#&lt;length&gt; / #&lt;pitch&gt;]]
 #&lt;k&gt; = [#&lt;pitch&gt; / 360] ( helix k factor )
 #&lt;angle&gt; = 0    (initial starting angle)

 (start by moving absolutely to cut depth )
 g90 g1 v [#&lt;depth&gt;] f[#&lt;_feedrate&gt;]
 (loop through angles until max angle reached )
 g91
 o&lt;loop&gt; while [#&lt;angle&gt; LT #&lt;max_angle&gt;]
 g1 x[#&lt;k&gt; * #&lt;step&gt; ]  b[#&lt;step&gt;]
 #&lt;angle&gt; = [[#&lt;angle&gt;] + [#&lt;step&gt;]]
 o&lt;loop&gt; endwhile
 g90 g0 v [#&lt;_safeheight&gt;] (move cutter absolutely to safe height)
o&lt;helix&gt; endsub

(************ main program ************)
( set initial values to suit your own application)
#&lt;_pitch&gt;    = 60      (this value is the helix pitch )
#&lt;_length&gt;    = 50     (this value is the length of the helix )
#&lt;_step&gt;    = 1    (this is the angular step in degrees )
#&lt;_maxdepth&gt;    = -1     (depth of helix )
#&lt;_depthinc&gt;    = -1    (depth increment for each pass )
#&lt;_numhelices&gt;    = 5    (number of helix starts )

(my setup assuming that values x,y,b,v are all zero when starting)

#&lt;start_angle_inc&gt; = [360 / #&lt;_numhelices&gt;]
#&lt;curr_helix&gt; = 0;

(code cuts full depth of each helix before moving on to the next)
o&lt;helix_loop&gt; while [#&lt;curr_helix&gt; LT #&lt;_numhelices&gt;]
 #&lt;curr_depth&gt; = [#&lt;_depthinc&gt;]
 o&lt;depth_loop&gt; while [#&lt;curr_depth&gt; GE #&lt;_maxdepth&gt;]
   g90 g0 v[#&lt;_safeheight&gt;]
   g90 g0 x10 y0
   g90 g0 b[#&lt;curr_helix&gt; * #&lt;start_angle_inc&gt;] f[#&lt;_traverserate&gt;] (set initial position)
   o&lt;helix&gt; call [#&lt;_pitch&gt;] [#&lt;_length&gt;] [#&lt;_step&gt;] [#&lt;curr_depth&gt;]
   #&lt;curr_depth&gt; = [[#&lt;curr_depth&gt;] + [#&lt;_depthinc&gt;]]
o&lt;depth_loop&gt; endwhile
#&lt;curr_helix&gt; = [[#&lt;curr_helix&gt;] + 1]
o&lt;helix_loop&gt; endwhile
M2 (end program)</pre>
