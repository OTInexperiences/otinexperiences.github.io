---
layout: page
title: Explorations in Gear cutting Part 1
date: 2012-10-11 19:15:36 +0000
author: Alan
categories: []
tags: []
permalink: "/explorations-in-gear-cutting-part-1/"
original_url: http://ab48.uk/otblog/explorations-in-gear-cutting-part-1/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/explorations-in-gear-cutting-part-1/"
parent: "/miscellaneous/"
---
I am interested in using my rose engine to cut gears. This means that I first need to make a simple fly cutter with the correct outline to cut a gear tooth. Actually the cutter cuts out material to leave the space between any two gear teeth.

<a href="{{ '/assets/recovered/1aa819f0e5-04-img_0573.png' | relative_url }}"><img alt="" height="299" src="{{ '/assets/recovered/1aa819f0e5-04-img_0573.png' | relative_url }}" title="04-img_0573" width="439"/></a>
<h2>Background</h2>
The standard way for a hobbyist to create a cutter (see Ivan Laws book, Gears and Gear Cutting, Workshop Practice Series) is a two step process. First you make a form tool by turning two buttons of the correct diameter  out of silver steel and fix them to a base a given distance apart. Then this tool is then used on the lathe to create the gear cutter blank which is then milled to create one or two teeth and finally hardened, tempered and sharpened.  This type of cutter needs to be attached to a shaft and rotated in the mill or lathe.

<a href="{{ '/assets/recovered/00318e8857-gear-cutter-tool.png' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1965" height="280" src="{{ '/assets/recovered/99bfd7a05e-gear-cutter-tool-300x280.png' | relative_url }}" title="gear cutter tool" width="300"/></a>

In his book  Mr Law includes two tables (pages 114-115) to enable you to calculate the button diameter and spacing for gears with 20 and 30 degree pressure angles. I asked on the <a href="http://groups.yahoo.com/group/mwmills2/" target="_blank">mwmills2</a> forum if anyone knew how to obtain these values for other pressure angles. Gail uploaded a spreadsheet that did the job perfectly. I have just added a couple of extra bits, to indicate what Diametral Pitch (DP) value you would get using a milling cutter of a specified diameter and also added conversions for values into millimeters and give module equivalents of DP values. I did this because my mill and its DRO are metric.

My adapted version of the spreadsheet in <a href="http://www.openoffice.org/">Open Office</a> format is  <a href="{{ '/assets/recovered/dc8118502e-GearCutters-Spreadsheet.zip' | relative_url }}">GearCutters Spreadsheet</a>
<h2>My Cutter</h2>
I needed to make a cutter blank that would fit in my cutting frame  and so had to be made from a piece of flat gauge plate as  I wanted to machine the correct form directly on my mill using a milling cutter  instead of having to make a pair of  silver steel buttons (see image above).

The largest mill cutter I have is 16mm in diameter, entering this data into the spreadsheet told me that the resulting teeth would be 21.718 DP or 0.855 module.

<a href="{{ '/assets/recovered/9dfcb09bb5-spread1.png' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1969" height="78" src="{{ '/assets/recovered/0dfcc63a88-spread1-300x78.png' | relative_url }}" title="spread1" width="300"/></a>

This non standard size does not bother me at all as I am making gears that run against each other and of course any two gears with the same DP or module value should mesh correctly.

<a href="{{ '/assets/recovered/b629d203b6-spread22.png' | relative_url }}"><img alt="" class="aligncenter size-full wp-image-1972" height="525" src="{{ '/assets/recovered/b629d203b6-spread22.png' | relative_url }}" title="spread2" width="916"/></a>

Putting this value into the original bit of the spreadsheet  gave me the correct button centre spacing and in-feed values to use with my 16mm diameter cutter.
<h2>Making the cutter</h2>
I put a sacrificial piece of aluminum into the vice on my mill table and milled a 25.5mm slot into it which is the same width as my gauge plate. Into this slot I placed my piece of gauge plate and held it with a toolmakers clamp. I milled the base of the gauge plate square and set my DRO X  axis value to zero. Having previously zeroed the DRO Y axis value to the centre of my slot I was then able to first move the mill table to 8.232mm along Y and feed the table along the X axis by the required amount of 6.407 mm specified on the spreadsheet, to cut the first half of the fly cutter. This was the repeated with the Y axis value set at -8.232mm to cut the second half. Finally the cutter body was milled to 12mm wide to fit in my cutting frame head. Finally it was hardened and sharpened.

(Previously I would usually also temper the cutters by putting it the oven at 240 deg C for 30 minutes. But John Edwards at the SOT told me that he does not usually bother with tempering his cutters as the cuts in OT are mainly small, through wood and do not chip the cutter. So I have decided to try using the untempered cutter as an experiment).
<h2>Holding the gear blank</h2>
The last piece of equipment I had to make was a mandrel to hold the gear blanks securely on the chuck. I faced a scrap piece of aluminium and turned a recess to enable it to fit securely in my wood turning chuck and act as a base.  I then drilled an 8mm hole through the centre, then bored out a location hole 15mm diameter and 10mm deep.  I machined a piece of steel rod to 15mm diameter as a close fit to the bore of the base and tapped each end to fit an m6 thread. Finally I turned half the length of this mandrel to 10mm diameter. The mandrel fits accurately in the base and is held by an m6 cap head bolt, the blank is placed on the 10mm end and held firmly against the shoulder again by an m6 cap head bold and washer. I am sure you could come up with a better version, but this at least allows me to make several mandrels with different bores to fit a range of gear blank sizes.

<a href="{{ '/assets/recovered/9b545bc11d-08-IMG_0577.png' | relative_url }}"><img alt="" class="aligncenter size-full wp-image-1961" height="372" src="{{ '/assets/recovered/9b545bc11d-08-IMG_0577.png' | relative_url }}" title="08-IMG_0577" width="495"/></a>
<h2>Cutting the gear first try</h2>
I also added  a table that calculated the gear blank diameters for a range of teeth sizes see example below (of course in this case teeth numbers above 73 are invalid).

<a href="{{ '/assets/recovered/390f238598-spread31.png' | relative_url }}"><img alt="" height="461" src="{{ '/assets/recovered/390f238598-spread31.png' | relative_url }}" title="spread3" width="319"/></a>

Finally I was in a position to try cutting a gear so I placed a bit of wood on my wood lathe and turned it to 49mm diameter and drilled a 10mm hole through it, fixed it to my mandrel and ran the simple G code program.
<h2><a href="{{ '/assets/recovered/6d32fb9392-03-IMG_05681.png' | relative_url }}"><img alt="" class="aligncenter size-medium wp-image-1977" height="226" src="{{ '/assets/recovered/f4b724032b-03-IMG_05681-300x226.png' | relative_url }}" title="03-IMG_0568" width="300"/></a>
The G code Program</h2>
The simple program I wrote assumes that the blank rotates around the B axis, Moves past the cutting frame along the Y axis and that the cutting frame moves towards the mandrel centre along the X axis.  Also at the start the cutter is just touching the blank and that this is the X zero position and is positioned beyond the end of the blank at the Y zero position. The rotation axis is also set at zero.

The program is a simple loop that repeatedly
<ol>
<li>makes a linear move to rotate the blank through the required angle.</li>
<li>makes a linear move sending the cutting frame towards the mandrel centre by the specified in-feed amount</li>
<li>makes a linear move to send the width of the  blank across the cutting frame.</li>
<li>makes a quick move to send the cutting frame back to its zero position.</li>
<li>makes a quick move to send the gear blank back to its zero position.</li>
<li></li>
</ol>
This set of moves is repeated once for each tooth.
<pre>(Example of cutting 40 tooth gear )
g21 g40 g49 g54 g80 g90 g94

#&lt;infeed&gt; = -2.624(depth of tooth cutter depth=0 when touching blank)
#&lt;Nteeth&gt; = 40    (Number of teeth in gear )
#&lt;Width&gt; = 65     (Width of gear )
#&lt;Feed&gt;  = 100    (feedrate)

#&lt;angle&gt; = [360.0 / #&lt;Nteeth&gt;]
#&lt;count&gt; = 0

(assumption is that at start cutter is beyond edge of gear blank)
g0 x0 y0 b0
o100 while [#&lt;count&gt; lt #&lt;Nteeth&gt;]
g1 B[#&lt;angle&gt; * #&lt;count&gt;] f[#&lt;feed&gt;]
g0 X[#&lt;infeed&gt;]
g1 Y [#&lt;Width&gt;]
g0 x0
g0 Y0
#&lt;count&gt; = [#&lt;count&gt; + 1]
o100 endwhile

g0 x0 y0 b0
M2</pre>
