---
layout: post
title: I suppose I should now call this Rose Mk3
date: 2012-08-06 21:40:49 +0000
author: Alan
categories:
- Rose Engine Build
tags: []
permalink: "/blog/i-suppose-i-should-now-call-this-rose-mk3/"
original_url: http://ab48.uk/otblog/i-suppose-i-should-now-call-this-rose-mk3/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/i-suppose-i-should-now-call-this-rose-mk3/"
  - "/otblog/i-suppose-i-should-now-call-this-rose-mk3/"
---
Over the last couple of weeks I have been building a beefier tool post in order to cut out some vibration problems when cutting patterns. Advice from a couple of people recently confirmed what I suspected that the 16mm linear rail supporting the tool post was not large enough.  I had some 25mm rail I was using for another project (cannibalized now for this build) so I decided to make some rather drastic changes that I had been considering for a while.

I have separated the headstock and tool post into two individual and unconnected assemblies. This allowed me to lower the table the tool post sat on and in doing so I have   the extra height to sit the tool post on a rotary table giving me the ability to change the orientation of the tool.

Also as I was making these major changes I decided to return to renaming my axes in the standard  way.  The result is that now my headstock has three degrees of freedom, it has linear movement along the Z and X axes and can rotate around the Z axis. Whilst the tool post also has 3 degrees of freedom, it has linear movement in the depth direction, vertical movement along the Y axis and rotary movement around the Y axis.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/dd97cb7a10-5-IMG_0283.png' | relative_url }}"><img alt="" class="size-medium wp-image-1945" height="232" src="{{ '/assets/recovered/a00555fda1-5-IMG_0283-300x232.png' | relative_url }}" title="5-IMG_0283" width="300"/></a>
<figcaption>Rose engine now in two parts</figcaption>
</figure>

The construction is complete except for wiring up the Y axis and rotary table steppers. Both of these are held by simple brackets which will be replaced at some future date. I now have to upgrade my electronics from a 4 axis to a 6 axis system.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/4895ecfeb9-headstock-axes.png' | relative_url }}"><img alt="" class="wp-image-1951" height="232" src="{{ '/assets/recovered/9142700e28-headstock-axes-300x290.png' | relative_url }}" title="headstock axes" width="240"/></a>
<figcaption>Headstock movement</figcaption>
</figure>

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/3c5a383c6b-tool-post.png' | relative_url }}"><img alt="" class="wp-image-1952" height="240" src="{{ '/assets/recovered/4d2938b272-tool-post-228x300.png' | relative_url }}" title="tool-post" width="182"/></a>
<figcaption>Tool post movement</figcaption>
</figure>

 

 

 

 

 

 

 

It is unfortunate that the centre of rotation does not correspond with the centre of the cutter. I shall have to compensate for this in software whenever I want a rotation around the cutter tip.
