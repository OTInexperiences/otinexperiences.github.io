---
layout: page
title: Spindle phase example
date: 2011-07-30 20:21:11 +0000
author: Alan
categories: []
tags: []
permalink: "/spindle-phase-example/"
original_url: http://ab48.uk/otblog/spindle-phase-example/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/spindle-phase-example/"
---
<h2>Main Program section</h2>
<pre>(---------------------- Start of main program --------------------------)
#&lt;_UseRotary&gt;        = 1    (we are using a rotary machine    )
#&lt;_UseMainSpindle&gt;   = 1    (we are using main spindle        )
#&lt;_UsePumpSpindle&gt;   = 0    ( not using pump                  )
#&lt;_UseChuck&gt;         = 0    (not using a chuck                )
#&lt;_UseBlending&gt;      = 0    (blending rosettes                )
#&lt;_ToolOffset&gt;       = 0    (tool at centre of work           )
#&lt;_Safeheight&gt;       = 2    (Safe height                      )
#&lt;_Feedrate&gt;         = 60   (feed rate for inverse time mode  )
#&lt;depth&gt;             = -2   ( depth of cutter during pass     )

( now must add at least one rosette to the spindle            )
##&lt;_MainSpindle&gt; = 0        ( spindle is empty                )
##&lt;_PumpSpindle&gt; = 0

o&lt;CreateWaveRosette&gt; call [100] [6] [25] [0] [1] [1]
o&lt;AddRosetteToSpindle&gt; call [#&lt;_MainSpindle&gt;] [#&lt;_result&gt;]

o&lt;ifmain1&gt; if [#&lt;_UseRotary&gt; GT 0 ]
    g93  (inverse time mode )
o&lt;ifmain1&gt; endif

o&lt;Generate_Path&gt; call [0] [1] [360] [#&lt;_Feedrate&gt;] [#&lt;_ToolOffset&gt;] [#&lt;depth&gt;] [0] [0]
o&lt;Generate_Path&gt; call [0] [1] [360] [#&lt;_Feedrate&gt;] [#&lt;_ToolOffset&gt;] [#&lt;depth&gt;] [15] [0]

g0 x0 b0 v[#&lt;_Safeheight&gt;]
M2</pre>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-1295" height="300" src="/assets/placeholder-original-image.svg" title="preplot1" width="300"/></a>
<figcaption>emc plot of path</figcaption>
</figure>

 
