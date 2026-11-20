---
layout: page
title: Using emc parameters - relative example
date: 2011-07-17 12:40:19 +0000
author: Alan
categories: []
tags: []
permalink: "/using-emc-parameters-relative-example/"
original_url: http://ab48.uk/otblog/using-emc-parameters-relative-example/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/using-emc-parameters-relative-example/"
---
(main program for application Myproject)
(global data for realtest1 )
#&lt;_return&gt;       = #31
#&lt;_index&gt;         = #32
#&lt;_lastmain&gt;    = #33
#&lt;_lastpump&gt;  = #34

(Machining Data)
#40 = 2     (Rough Cut Increment)
#41 = 1     (Finish Cut Increment)
#43 = 40     (Linear Feed Rate)
#44 = 90     (Inverse Time Feed Rate)
#45 = 1     (Use MM units flag)
#46 = 5     (Safe Height)

( location of start of main spindle offset data )
#&lt;_mainlength&gt;         = 1000
#&lt;_main_angle_inc&gt;     = 1001
(next few reserved area )
#&lt;_main&gt;             = 1005

( location of start of pump spindle offset data )
#&lt;_pumplength&gt;         = 3000
#&lt;_pump_angle_inc&gt;     = 3001
(next few reserved area)
#&lt;_pump&gt;             = 3005
(----------------------------)
o&lt;realtest1_memmap&gt; call   (Initialise table data )
(----------------------------)
(now for main program loop    )
(which runs indefinitely    )
#&lt;_index&gt; = 1
g93 g21 g91

o&lt;mainloop&gt; while [1]

(get values from main table and make move)
#10 = #[#&lt;_main&gt; + #&lt;_index&gt;]
#11 = #[#&lt;_pump&gt; + #&lt;_index&gt;]
g1 X[#10 - #&lt;_lastmain&gt;] Y[#11 - #&lt;_lastpump&gt;] B[##&lt;_main_angle_inc&gt;] f[#44]
#&lt;_lastmain&gt; = [#10]
#&lt;_lastpump&gt; = [#11]
#&lt;_index&gt; =[ [#&lt;_index&gt; + 1 ] MOD ##&lt;_mainlength&gt;]

o&lt;if1&gt; if [#&lt;_index&gt; EQ 1]  (completed first rotation so stop plotting)
(AXIS,stop)
o&lt;if1&gt; endif
o&lt;mainloop&gt; endwhile
M2
