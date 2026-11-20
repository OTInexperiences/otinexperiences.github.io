---
layout: page
title: Spiral pattern described by Bill Ooms
date: 2011-10-02 17:31:23 +0000
author: Alan
categories: []
tags: []
permalink: "/spiral-pattern-described-by-bill-ooms/"
original_url: http://ab48.uk/otblog/spiral-pattern-described-by-bill-ooms/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/spiral-pattern-described-by-bill-ooms/"
---
Here is the main part of the GRose program that was used to cut the box lid shown below.

<a href="{{ '/assets/recovered/2b17e23168-IMG_0803.jpg' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1627" height="284" src="{{ '/assets/recovered/55837ee582-IMG_0803-300x284.jpg' | relative_url }}" title="IMG_0803" width="300"/></a>The pattern was described by Bill Ooms in the Fall 2010 OTI newsletter.

The main program is
<pre>#&lt;amplitude&gt; = 2    (max amplitude of pumping action)
#&lt;lobes&gt;     = 7    (number of lobes in pattern )
#&lt;offset&gt;    = 3    (distance cutter moves after each pass )
#&lt;count&gt;     = 24   (number of repetitions )

o&lt;CreateWaveRosette&gt; call [0] [#&lt;lobes&gt;] [#&lt;amplitude&gt;] [0] [0] [1]    (r1, f,  a,  abs,  ph, bl)
o&lt;AddRosetteToSpindle&gt; call [#&lt;_PumpSpindle&gt;] [#&lt;_result&gt;]
(******************* Now create paths ***********************************)
o&lt;main1&gt; if [#&lt;_UseRotary&gt; EQ 1]
    g93  (Inverse time mode )
o&lt;main1&gt; endif
g61  (exact path mode )
o&lt;loop&gt; repeat [#&lt;count&gt;]
o&lt;MoveToSafeHeight&gt; call
g0 y0 b0
g1 x [#&lt;ToolOffset&gt;] f[#&lt;Feedrate&gt;]
o&lt;Generate_Path&gt; call [0] [1] [365 ] [#&lt;Feedrate&gt;] [#&lt;ToolOffset&gt;] [#&lt;Depth&gt;] [0] [#&lt;Phase&gt;]
o&lt;MoveToSafeHeight&gt; call
g0 y[-#&lt;amplitude&gt;]
#&lt;ToolOffset&gt; = [#&lt;ToolOffset&gt; + #&lt;offset&gt;]
#&lt;Phase&gt; = [#&lt;Phase&gt; + 90 ]
o&lt;MoveToSafeHeight&gt; call
o&lt;loop&gt; endrepeat
g0 x0 b0
M2</pre>
To have the spiral rotate in the opposite direction subtract 90 from the phase instead of adding it.  Also the 24 repeats are sufficient to cover the whole of the 100mm x 100mm area of the piece. Adjust this number accordingly dependent on the value of #&lt;offset&gt; and the size of your work.
