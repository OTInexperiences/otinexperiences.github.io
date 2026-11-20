---
layout: page
title: Cutting a wave pattern along the side of a piece
date: 2011-07-28 19:58:36 +0000
author: Alan
categories: []
tags: []
permalink: "/cutting-a-wave-pattern-along-the-side-of-a-piece/"
original_url: http://ab48.uk/otblog/cutting-a-wave-pattern-along-the-side-of-a-piece/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/cutting-a-wave-pattern-along-the-side-of-a-piece/"
---
In my earlier examples (1 and 2) the cutter was facing towards the chuck what a woodturner would call face work.  Therefore its depth movement was parallel but opposite to the longtitudinal movement of the spindle along my Y axis, and the work only moved laterally along the X axis. This meant that the resultant pattern was cut around the side of the piece as the spindle rotated.

In this example the wave pattern is cut longtitudinally so that each wave seems to go from the top to the bottom of the piece not around it. Therefore the cutter depth direction must be into the side of the work along the -X direction. To make the wave the spindle moves along its  longtitudinal axis here Y whilst the spindle axis B is rotated by a small amount from its mean position.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-1281" height="294" src="/assets/placeholder-original-image.svg" title="wavyedge1" width="300"/></a>
<figcaption>emc pre plot of paths</figcaption>
</figure>

The amount of rotation the spindle makes from its nominal angular position is calculated by multiplying an amplitude value by a  sine function whose angle is proportional to the distance moved along the Y axis and then converting this value to degrees and dividing by the radius of the piece.

So if  y=0 the angle parameter of sin is 0 and then when y = L the angle parameter of sin is 360 degrees.

so height of wave  = Amplitude  * sin ( Frequency * 360 * y / L)

now converting so that angle of wave = height of wave * 180 / pi * radius of piece.  Hence we move the B axis to Current Angle +  angle of wave
<pre>(Example ofcutting a path alongthe side of a box
#&lt;_rad&gt; = [180 / 3.142]

(This is the task to perform at each indexed position)
(Remember when this task is called we are at safe height)
(This task cuts a wave along the piece by altering the angle B based on the length Y )
(parameter #1 is the depth of the cut )
o&lt;dowave&gt; sub      (param #1 is frequency of wave  )
        (param #2 is amplitude of wave             )
        (param #3 is length of piece L             )
        (param #4 is y increment                   )
        (param #5 is radius of piece r             )
        (param #6 is the current angle for B       )
        (param #7 is current depth                 )
        (param #8 is feed rate                     )
        (local #9 is current y                     )
        (local #10 is 360 / L                      )
        (local #11 is height of wave at position #9)
        (local #12 is this value as an angle       )

    #9 = 0
    #10 = [360 / #3]      (angle inc for change in unit length)
    g90 g0 y[#9]        (go to start )
    g90 g1 v[#7] f[#8]    (move to current depth)
    o&lt;yloop&gt; while [#9 LE #3]
        #11 = [#2 * sin[#1 * #10 * #9] ] (current amp of wave at psn #9)
        #12 = [#11 * #&lt;_rad&gt; / #5]  (angle to adjust B by )
        g90 g1 y[#9] b[#6 + #12 ] f[#8]
    #9 = [#9 + #4]
    o&lt;yloop&gt; endwhile
    g90 g0 v[#&lt;_safeheight&gt;]
o&lt;dowave&gt; endsub

(************ main program *********)
#&lt;_startdepth&gt;  = -0.5    (start cutting at this depth)
#&lt;_maxdepth&gt;    = -4      (depth of helix )
#&lt;_depthinc&gt;    = -0.5    (depth increment for each pass )

#&lt;_angleinc&gt;    = 15      (angle increment)
#&lt;_angle&gt;       = 0       (angle to index to)
#&lt;_anglemax&gt;    = 360     (last angle to index to)
#&lt;_feedrate&gt;    = 60      ( feed rate )
(next value is to make pattern visible in emc)
(dont forget to touch off x by this amount)
g90 g0 x70

o&lt;patloop&gt; while [#&lt;_angle&gt; LT #&lt;_anglemax&gt;]
g90 g0 v[#&lt;_safeheight&gt;]
g0 B[#&lt;_angle&gt;]
#&lt;curr_depth&gt; = [#&lt;_startdepth&gt;]

o&lt;depth_loop&gt; while [#&lt;curr_depth&gt; GE #&lt;_maxdepth&gt;]
           o&lt;dowave&gt; call [1]  [15] [80] [0.1] [70] [#&lt;_angle&gt;] [#&lt;curr_depth&gt;] [#&lt;_feedrate&gt;]
    #&lt;curr_depth&gt; = [[#&lt;curr_depth&gt;] + [#&lt;_depthinc&gt;]]
o&lt;depth_loop&gt; endwhile
g90 g0 v[#&lt;_safeheight&gt;]
#&lt;_angle&gt; = [#&lt;_angle&gt; + #&lt;_angleinc&gt;]
o&lt;patloop&gt; endwhile
g90 g0 b0
M2</pre>
 
