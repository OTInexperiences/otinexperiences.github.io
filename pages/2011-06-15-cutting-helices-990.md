---
layout: page
title: Cutting Helices
date: 2011-06-15 21:27:42 +0000
author: Alan
categories: []
tags: []
permalink: "/software/g-code-examples/cutting-helices/"
original_url: http://ab48.uk/otblog/software/g-code-examples/cutting-helices/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/g-code-examples/cutting-helices/"
parent: "/software/g-code-examples/"
---
<pre>A helix is a screw thread see quick example below</pre>
<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/578694b449-IMG_0254.jpg' | relative_url }}"><img alt="helix example" class="size-medium wp-image-991" height="97" src="{{ '/assets/recovered/2a25e2844b-IMG_0254-300x97.jpg' | relative_url }}" title="IMG_0254" width="300"/></a>
<figcaption>Three start helix on piece of pine</figcaption>
</figure>

This was cut using the gcode shown below. The g code to cut this quite straightforward. For every degree the work turns the tool must move some distance (called K ) forward.

If the pitch of the helix is P and its length is L then we have

distance moved along = K * Angle turned where K = P / 360   Also

Yje maximum angle we need to turn through = (L / P ) * 360

This information is encapsulated in the following g code subroutine which uses named variables
<pre>o&lt;helix&gt; sub
 #&lt;pitch&gt;  = #1  (pitch of helix )
 #&lt;length&gt; = #2  (length of helix to cut - width of cutter)
 #&lt;step&gt;   = #3  (angular step )
 #&lt;depth&gt;  = #4  (depth to cut )

 (first caluculate some required values for local variables)
 #&lt;max_angle&gt; = [ 360 * [#&lt;length&gt; / #&lt;pitch&gt;]]
 #&lt;k&gt; = [#&lt;pitch&gt; / 360] ( helix k factor )
 #&lt;angle&gt; = 0    (initial starting angle)

 (start by moving absolutely to cut depth )
 g90 g1 u [#&lt;depth&gt;]
 (loop incrementally through angles until max angle reached )
 g91
 o&lt;loop&gt; while [#&lt;angle&gt; LT #&lt;max_angle&gt;]
     g1 y-[#&lt;k&gt; * #&lt;step&gt; ]  b[#&lt;step&gt;]
     #&lt;angle&gt; = [[#&lt;angle&gt;] + [#&lt;step&gt;]]
 o&lt;loop&gt; endwhile
 g90 g0 u [#&lt;_safeheight&gt;] (move cutter absolutely to safe height)
o&lt;helix&gt; endsub</pre>
<h2>Properties we need</h2>
<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-medium wp-image-992" height="355" src="/assets/placeholder-original-image.svg" title="helix figure" width="241"/></a>

We need to give
<ol>
<li>The total length of the helix we wish to cut. This figure must include an allowance for the width of the cutter. That is if we wanted a helix 100mm long to be cut with a cutter 5mm wide we need to give the length as 95mm</li>
<li>The pitch of the helix. This is the amount we move along for one complete turn of the work. So for example if our helix had 4 complete revolutions in its 100mm length then its pitch would be 25mm.</li>
<li>The angle steps to take when cutting the helix.</li>
<li>The depth to cut.</li>
</ol>
As we have seen above these values are passed as parameters to our subroutine when it is called as in the example below

o&lt;helix&gt; call [#&lt;_pitch&gt;] [#&lt;_length&gt;] [#&lt;_step&gt;] [#&lt;curr_depth&gt;]

Of course we may need several passes in order to cut the helix to the correct depth. In the code fragment below the call to generate the helix is placed inside a simple loop that uses a variable to hold the value of the current depth and increments that value each time around the loop stopping when the desired depth has been reached. Note that depths are assumed to be negative.
<pre>#&lt;curr_depth&gt; = [#&lt;_depthinc&gt;]
 o&lt;depth_loop&gt; while [#&lt;curr_depth&gt; GE #&lt;_maxdepth&gt;]
     g90 g0 [#&lt;_safeheight&gt;]
     g90 g0 x0 y0
     g90 g0 b[#&lt;curr_helix&gt; * #&lt;start_angle_inc&gt;] f20  (set initial position)
     o&lt;helix&gt; call [#&lt;_pitch&gt;] [#&lt;_length&gt;] [#&lt;_step&gt;] [#&lt;curr_depth&gt;]
     #&lt;curr_depth&gt; = [[#&lt;curr_depth&gt;] + [#&lt;_depthinc&gt;]]
 o&lt;depth_loop&gt; endwhile</pre>
Finally you may wish to cut more than one helix around the piece so the code above is enclosed in a loop to do just that. So the complete program is shown below
<pre>(Author Alan Battersby)
(Program to cut a helix along the -Y axis as given by my machine setup)

(Comment - Note this is not for a standard Mill. )
(In my setup the cutter depth axis is U )
(Also the helix rotates around the Y axis, here I use B)

(set some global values )
G21 G40 G49 G54 G80 G90 G94
#&lt;_safeheight&gt; = 5

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
 g90 g1 u [#&lt;depth&gt;]
 (loop through angles until max angle reached )
 g91
 o&lt;loop&gt; while [#&lt;angle&gt; LT #&lt;max_angle&gt;]
 g1 y-[#&lt;k&gt; * #&lt;step&gt; ]  b[#&lt;step&gt;]
 #&lt;angle&gt; = [[#&lt;angle&gt;] + [#&lt;step&gt;]]
 o&lt;loop&gt; endwhile
 g90 g0 u [#&lt;_safeheight&gt;] (move cutter absolutely to safe height)
o&lt;helix&gt; endsub

(************ main program ************)
( set initial values to suit your own application)
#&lt;_pitch&gt;      = 25   (this value is the helix pitch )
#&lt;_length&gt;     = 100  (this value is the length of the helix )
#&lt;_step&gt;       = 1    (this is the angular step in degrees )
#&lt;_maxdepth&gt;   = -3   (depth of helix )
#&lt;_depthinc&gt;   = -1   (depth increment for each pass )
#&lt;_numhelices&gt; = 1    (number of helix starts )

(my setup assuming that values x,y,u,b are all zero when starting)

#&lt;start_angle_inc&gt; = [360 / #&lt;_numhelices&gt;]
#&lt;curr_helix&gt; = 0;

(code cuts full depth of each helix before moving on to the next)
o&lt;helix_loop&gt; while [#&lt;curr_helix&gt; LT #&lt;_numhelices&gt;]
   #&lt;curr_depth&gt; = [#&lt;_depthinc&gt;]
   o&lt;depth_loop&gt; while [#&lt;curr_depth&gt; GE #&lt;_maxdepth&gt;]
     g90 g0 u[#&lt;_safeheight&gt;]    �
     g90 g0 x0 y0
     g90 g0 b[#&lt;curr_helix&gt; * #&lt;start_angle_inc&gt;] f20  (set initial position)
     o&lt;helix&gt; call [#&lt;_pitch&gt;] [#&lt;_length&gt;] [#&lt;_step&gt;] [#&lt;curr_depth&gt;]
     #&lt;curr_depth&gt; = [[#&lt;curr_depth&gt;] + [#&lt;_depthinc&gt;]]
   o&lt;depth_loop&gt; endwhile
   #&lt;curr_helix&gt; = [[#&lt;curr_helix&gt;] + 1]
o&lt;helix_loop&gt; endwhile
M2 (end program)</pre>
Here are some images of the plot in emc
<p style="text-align: center;"> </p>


<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/fe5a9a781d-helix1.png' | relative_url }}"><img alt="Emc plot of single helix" class="size-medium wp-image-994" height="230" src="{{ '/assets/recovered/24b573f279-helix1-300x230.png' | relative_url }}" title="helix1" width="300"/></a>
<figcaption>Emc plot of a single helix</figcaption>
</figure>

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/8b972bdfbf-helix1-3.png' | relative_url }}"><img alt="Emc of single helix with several depth passes" class="size-medium wp-image-995" height="233" src="{{ '/assets/recovered/69bf3d6526-helix1-3-300x233.png' | relative_url }}" title="helix1-3" width="300"/></a>
<figcaption>Emc of single helix with several depth passes</figcaption>
</figure>
<p style="text-align: center;"> </p>


<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/13392b3ac4-helix2.png' | relative_url }}"><img alt="Emc of two helices that is a two start thread" class="size-medium wp-image-996" height="232" src="{{ '/assets/recovered/42e8c6edf5-helix2-300x232.png' | relative_url }}" title="helix2" width="300"/></a>
<figcaption>Emc of two helices</figcaption>
</figure>

 
