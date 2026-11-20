---
layout: page
title: Grose for use on a standard mill
date: 2013-04-15 21:42:30 +0000
author: Alan
categories: []
tags: []
permalink: "/grose-for-use-on-a-standard-mill/"
original_url: http://ab48.uk/otblog/grose-for-use-on-a-standard-mill/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/grose-for-use-on-a-standard-mill/"
---
This is a simplified version of Grose for use on a standard milling machine. No rotary table is needed. The workpiece moves in the standard XY plane and the cutting frame is assumed to be the mill head acting along the Z axis perpendicular to the table. Therefore this version is only really suitable for face work such as cutting a pattern on the top or bottom of a bowl, box etc.

Download this code <a href="http://www.ab48.uk/otblog/wp-content/uploads/2013/04/grose_XYZ_with_profile.txt">grose_XYZ_with_profile   </a>and rename to .ngc
The program supports movement along a linear profile swept out around the Z axis. This profile is defined as a sequence of equally spaced height points along some given range. Linear interpolation is used to get the height of a position lying between two adjacent points.

Three library functions are initially provided to allow simple surfaces to be generated.
<ol>
<li>
<h3>Linear</h3>
<a href="{{ '/assets/recovered/e4deaf5ca5-Screenshot3.png' | relative_url }}"><img alt="Screenshot3" class="wp-image-2174 alignnone" height="321" src="{{ '/assets/recovered/e4deaf5ca5-Screenshot3.png' | relative_url }}" width="331"/></a></li>
<li>
<h3>Cup</h3>
<a href="{{ '/assets/recovered/cf50b0b4dd-Screenshot1.png' | relative_url }}"><img alt="cup" class="alignnone wp-image-2175" height="319" src="{{ '/assets/recovered/cf50b0b4dd-Screenshot1.png' | relative_url }}" width="329"/></a></li>
<li>
<h3>Cap</h3>
<a href="/assets/placeholder-original-image.svg"><img alt="cap" class="alignnone wp-image-2176" height="320" src="/assets/placeholder-original-image.svg" width="329"/></a></li>
</ol>
The first three parameters of the built in profile generators are the same being that

#1 =<em><strong> start</strong></em>, #2 = <strong><em>increment</em></strong> and #3 = <strong><em>end</em></strong> values of the base range .  Any value outside this range that is  less than <em><strong>start</strong></em> and greater than <em><strong>end</strong></em> will have a height of zero.  The increment value determines how many points there are in the profile.

For the  Linear profile #4 = left end height #5= right end height     strictly there only need by the two end points so that a call such as
<pre>o&lt;Linear&gt; call  [0] [55] [55] [0] [-20]</pre>
is perfectly legal and will produce a slope varying from 0 to -20 between x=0 and x=55. Values are unit free and can be decimal .

You can specify a range say from -20 to 20 and this is fine but it will not vary with Y so the surface will be a plane.

For both the Cap  and Cup profiles #4 = <em><strong>cap height</strong></em> #5 = <em><strong>optional offset</strong></em>. Both are based on generating the heights for a circular section  given its centre height which is the value of #4 and  the length of its base chord given by the length of the range i.e #3 - #2.  So the centre (highest/lowest point) of the profile will always be at the midpoint in the range.

For example if you make the value of #4 equal to half the range length you will get a hemispherical surface. The fifth parameter allows you to move the surface up or down in the vertical axis. So for example if you want the top of the cap to be at zero on the z axis you should make the offset equal to minus the cap height.
<pre>o&lt;Cap&gt; call [-50] [1] [50] [10] [-10]</pre>
The call above will generate a cap centered at X=0 Y=0 with height Z=0 at that point.

Please note that generally there are three flag values to set when using a profile.
<pre>#&lt;_IsRadialProfile&gt;   = 1    (Using a radial profile     )
#&lt;_ProfileInZ&gt;        = 1    (profile in Z direction     )
#&lt;_UseProfile&gt;        = 1    (Definitely using a profile )</pre>
I hope to soon have optional code that will enable you to run a depth probe across an existing surface and use those depth values as the profile data.

 
