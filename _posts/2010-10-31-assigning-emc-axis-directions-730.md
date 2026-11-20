---
layout: post
title: Assigning Emc axis directions
date: 2010-10-31 16:28:50 +0000
author: Alan
categories:
- Uncategorized
tags: []
permalink: "/blog/assigning-emc-axis-directions/"
original_url: http://ab48.uk/otblog/assigning-emc-axis-directions/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/assigning-emc-axis-directions/"
  - "/otblog/assigning-emc-axis-directions/"
---
Now that I have added  a movable tool post , this has given me an extra degree of freedom of movement.
<p style="text-align: center;"><a href="http://otinexperiences.co.uk/blog/wp-content/uploads/2010/10/assign_axes.jpg"><img alt="" class="aligncenter size-full wp-image-729" height="361" src="/assets/placeholder-original-image.svg" title="assign_axes" width="795"/></a></p>
<p style="text-align: center;"></p>
<p style="text-align: left;">The problem is to assign axes so that emc's axis view would give a sensible image in its path plotting display.</p>
<p style="text-align: left;">For many simple patterns I can keep the same axis assignment as I had before I added the movable tool post because I will not be using the pumping movement. However when using pumping and cutting on a face I will have two motions in the the same (possibly directly opposite) direction being driven by different steppers. In this case I was thinking of assigning Z for tool cutting direction, X as radial movement as before, but now Y for headstock movement and thus B for headstock rotation. So here Y and Z would be in the same or diectly opposite directions!! It doesn't sound right does it what should I do in order to get emc's axis to correctly represent what is happening?</p>
<p style="text-align: left;">I dont know yet. After asking advice on the emc list I think I have decided on the image below</p>
<p style="text-align: center;"><a href="http://otinexperiences.co.uk/blog/wp-content/uploads/2010/10/assign_axes2.jpg"><img alt="" class="aligncenter size-full wp-image-733" height="378" src="/assets/placeholder-original-image.svg" title="assign_axes2" width="786"/></a></p>
<p style="text-align: left;"></p>
<p style="text-align: left;">Which I hope gives the geometry of CXZBW suggested by Andy Pugh.</p>
