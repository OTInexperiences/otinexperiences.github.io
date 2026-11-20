---
layout: page
title: Example using a repeat
date: 2011-08-01 21:37:49 +0000
author: Alan
categories: []
tags: []
permalink: "/example-using-a-repeat/"
original_url: http://ab48.uk/otblog/example-using-a-repeat/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/example-using-a-repeat/"
---
This is a repeat of an earlier program but this time using RoseG.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-1302" height="300" src="/assets/placeholder-original-image.svg" title="badge3" width="280"/></a>
<figcaption>emc pre-plot of path</figcaption>
</figure>
<h3>Program fragment</h3>
<pre>(---------------------- Start of main program --------------------------)
#&lt;_UseRotary&gt;        = 1    (we are using a rotary machine              )
#&lt;_UseMainSpindle&gt;   = 1    (we are using main spindle                  )
#&lt;_UsePumpSpindle&gt;   = 0    ( not using pump                            )
#&lt;_UseChuck&gt;         = 0    (not using a chuck                          )
#&lt;_UseBlending&gt;      = 0    (blending rosettes                          )

(---------------------- Local variables-------------------------------- )
#&lt;ToolOffset&gt;        = 0    (tool at centre of work     )
#&lt;Safeheight&gt;        = 2    (Safe height                )
#&lt;Phase&gt;             = 0    ( local holding phase value )

( now must add at least one rosette to the spindle        )
##&lt;_MainSpindle&gt; = 0        ( spindle is empty            )
##&lt;_PumpSpindle&gt; = 0
o&lt;CreateWaveRosette&gt; call [100] [12] [25] [0] [1] [1]
o&lt;AddRosetteToSpindle&gt; call [#&lt;_MainSpindle&gt;] [#&lt;_result&gt;]

g93  (using rotary table so switch to inverse time mode )

o&lt;mainloop&gt; repeat [5]
    o&lt;Generate_Path&gt; call [0] [0.5] [360] [60] [#&lt;ToolOffset&gt;] [-2] [#&lt;Phase&gt;] [0]
    #&lt;Phase&gt; = [#&lt;Phase&gt; + 7.5]
    #&lt;ToolOffset&gt; = [ #&lt;ToolOffset&gt; - 25]
o&lt;mainloop&gt; endrepeat
g0 x0 b0 v[#&lt;Safeheight&gt;]

M2</pre>
