---
layout: page
title: Gcode for Badge
date: 2011-06-29 17:17:41 +0000
author: Alan
categories: []
tags: []
permalink: "/software/g-code-examples/gcode-for-badge/"
original_url: http://ab48.uk/otblog/software/g-code-examples/gcode-for-badge/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/g-code-examples/gcode-for-badge/"
parent: "/software/g-code-examples/"
---
This is the pattern I intend to cut on my test badge. See Emc pre-plot below. I started off hoping to get three rows of petals cut on the work but the innermost row was two squashed so I changed it to two.

<a href="{{ '/assets/recovered/925336080f-badge2.png' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1118" height="290" src="{{ '/assets/recovered/4e2f53bd27-badge2-300x290.png' | relative_url }}" title="badge2" width="300"/></a>

The code is
<pre>(Example of a rosette pattern)

(set some global values )
G21 G40 G49 G54 G80 G90 G94
#&lt;_safeheight&gt;     = 1
#&lt;_feedrate&gt;     = 60
#&lt;_invfeedrate&gt; = 40
#&lt;_result&gt;     = #31

(sub to generate a wave pattern around the spindle axis)
(returns its result in global #&lt;_result&gt; )
( formula is )
( amp = Amplitude * Sin[angle - phase]  )
( result =  [[absolute] ? Math.Abs[amp] : amp]] )
o&lt;wave_rosette&gt; sub
 #&lt;angle&gt;      = #1
 #&lt;amplitude&gt;  = #2
 #&lt;frequency&gt;  = #3
 #&lt;phase&gt;      = #4
 #&lt;absolute&gt;   = #5

 #&lt;_result&gt; = [#&lt;amplitude&gt; * sin[#&lt;frequency&gt; * [ #&lt;angle&gt; - [#&lt;phase&gt;]]]]
 o&lt;if1&gt; if [#&lt;absolute&gt; GT 0]
 #&lt;_result&gt; = abs[#&lt;_result&gt;]
 o&lt;if1&gt;  endif
o&lt;wave_rosette&gt; endsub

o&lt;RapidMove&gt; sub
 ( #1 is radius, #2 is angle, #3 is depth)
 g90 g0 V [#3]
 x [#1] b [#2]
o&lt;RapidMove&gt; endsub

o&lt;Cut_Path&gt; sub ( Cut one rotation finishing off at the safe height)
 ( #1 is angle increment)

 #&lt;angle&gt; = 0
 (move to first position without cutting)
 o&lt;wave_rosette&gt; call [#&lt;angle&gt;] [6] [6] [9] [1]
 #&lt;last_x&gt; = [#&lt;_result&gt;]
 #&lt;angle&gt; = [[#1] + [#&lt;angle&gt;]]
 g91 x[#&lt;last_x&gt;] f[#&lt;_feedrate&gt;]
 g90 g0 V[#&lt;_curr_depth&gt;] (depth)
 o&lt;angle_loop&gt; while [[#&lt;angle&gt;] LE 360]
 o&lt;wave_rosette&gt; call [#&lt;angle&gt;] [6] [6] [9] [1]
 g93 g91 g1 x[#&lt;_result&gt; - #&lt;last_x&gt;] b1 f[#&lt;_invfeedrate&gt;]
 #&lt;angle&gt; = [[#1] + [#&lt;angle&gt;]]
 #&lt;last_x&gt; = #&lt;_result&gt;
 o&lt;angle_loop&gt; endwhile
 g90 g0 V[#&lt;_safeheight&gt;]
o&lt;Cut_Path&gt; endsub

(************ main program *********)
#&lt;_maxdepth&gt;    = -0.5    (depth of helix )
#&lt;_depthinc&gt;    = -0.5    (depth increment for each pass )
#&lt;last_x&gt;    = 0    (last x value )
#&lt;_curr_depth&gt; = -0.5

o&lt;depth_loop&gt; while [#&lt;_curr_depth&gt; GE #&lt;_maxdepth&gt;]
 (will cut on 48mm diameter circle)
 o&lt;RapidMove&gt; call [18] [0] [#&lt;_safeheight&gt;]
 o&lt;Cut_Path&gt; call [1]
 o&lt;RapidMove&gt; call [12] [15] [#&lt;_safeheight&gt;]
 o&lt;Cut_Path&gt; call [1]
 #&lt;_curr_depth&gt; = [[#&lt;_curr_depth&gt;] + [#&lt;_depthinc&gt;]]
o&lt;depth_loop&gt; endwhile
o&lt;RapidMove&gt; call [0] [0] [#&lt;_safeheight&gt;]
M2</pre>
<a href="{{ '/assets/recovered/bfe74fa7b8-IMG_0367.jpg' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1178" height="300" src="{{ '/assets/recovered/0c13e90b4c-IMG_0367-268x300.jpg' | relative_url }}" title="IMG_0367" width="268"/></a>
