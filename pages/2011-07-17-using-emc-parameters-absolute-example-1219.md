---
layout: page
title: Using Emc parameters - absolute example
date: 2011-07-17 12:36:41 +0000
author: Alan
categories: []
tags: []
permalink: "/using-emc-parameters-absolute-example/"
original_url: http://ab48.uk/otblog/using-emc-parameters-absolute-example/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/using-emc-parameters-absolute-example/"
---
<pre>(main program for application realtest1)
(Using Absolute mode for path)
(global data for realtest1 )
#&lt;_return&gt;         = #31
#&lt;_index&gt;          = #32
#&lt;_lastmainval&gt;    = #33
#&lt;_lastpumpval&gt;    = #34
#&lt;_nturns&gt;         = #35

(Machining Data)
#&lt;_roughcut&gt;         = #40    (Rough Cut Increment)
#&lt;_finishcut&gt;        = #41     (Finish Cut Increment)
#&lt;_invfeedrate&gt;      = #42    (Inverse Time Feed Rate)
#&lt;_feedrate&gt;         = #43     (Linear Feed Rate)
#&lt;_useMM&gt;            = #44     (Use MM units flag)
#&lt;_safeheight&gt;       = #45     (Safe Height)
#&lt;_currentdepth&gt;     = #46    (Current cutting depth )

( location of start of main spindle offset data )
#&lt;_mainlength&gt;         = 1000
#&lt;_main_angle_inc&gt;     = 1001
(next few reserved area )
#&lt;_main&gt;               = 1005  

( location of start of pump spindle offset data )
#&lt;_pumplength&gt;         = 3000
#&lt;_pump_angle_inc&gt;     = 3001
(next few reserved area)
#&lt;_pump&gt;               = 3005
(******** End of Globals **************)

(----------------------------)
o&lt;realtest1_memmap&gt; call   (Initialise table data )
(----------------------------)
(Rapid move to position   )
(params are         )
(   #1 is AXIS1 usually radius value along offset axis    )
(   #2 is RAXIS0 usually angle around spindle axis     )
(   #3 is AXIS2 usually value along depth axis     )
o&lt;Rapidmove&gt; sub
g90 g0 V [#3]
g90 X [#1] B [#2]
o&lt;Rapidmove&gt; endsub

(Make a linear move in Absolute Mode         )
(Params are                      )
(    #1 = Depth to Move cutter to on AXIS2    )
(    #2 = Feedrate                )
o&lt;Movetodepth&gt; sub
g90 g1 V[#1]  F[#2]
o&lt;Movetodepth&gt; endsub

(----------------------------)
( set these variable values to suit )
(Set various variable values )
#&lt;_roughcut&gt;     = 1    (Rough Cut Increment)
#&lt;_finishcut&gt;    = 0.1     (Finish Cut Increment)
#&lt;_invfeedrate&gt; = 60    (Inverse Time Feed Rate)
#&lt;_feedrate&gt;    = 60     (Linear Feed Rate)

#&lt;_safeheight&gt;    = 10     (Safe Height)
#&lt;_currentdepth&gt; = -0.1  ( set to suit yourself )
#&lt;_nturns&gt; = 0        ( number of full rotations )

(---- Start of main program ----)
g93 g21  (Inv Time Mode + MM units )
g90
(go to first position in table at safe height at start angle usually 0)
o&lt;Rapidmove&gt; call [ ##&lt;_main&gt;] [0] [#&lt;_safeheight&gt;]

#&lt;_index&gt; = 0
o&lt;mainloop&gt; while [1]
    (get values from main table and make move)
    o&lt;if1&gt; if [#&lt;_index&gt; EQ 0] (if a safe height move to cut depth)
        o&lt;Movetodepth&gt; call  [#&lt;_currentdepth&gt;] [#&lt;_feedrate&gt;]
    o&lt;if1&gt; endif

    #10 = #[#&lt;_main&gt; + #&lt;_index&gt;]
    #&lt;angle&gt; = [[360 * #&lt;_nturns&gt;] + [##&lt;_main_angle_inc&gt; *  #&lt;_index&gt;]]
    g1 X[#10 ] B[#&lt;angle&gt;] f[#&lt;_invfeedrate&gt;]
    #&lt;_index&gt; =[ [#&lt;_index&gt; + 1 ] MOD ##&lt;_mainlength&gt;]

    o&lt;if2&gt; if [#&lt;_index&gt; EQ 0]
        (completed first rotation so stop plotting)
        #&lt;_nturns&gt; = [#&lt;_nturns&gt; + 1]
        (AXIS,stop)
    o&lt;if2&gt; endif
o&lt;mainloop&gt; endwhile
(return to home position)
o&lt;Rapidmove&gt; call [ 0] [0] [#&lt;_safeheight&gt;]
M2</pre>
