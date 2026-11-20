---
layout: page
title: Blending Rosettes
date: 2009-12-04 20:26:48 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/rosette/blending-rosettes/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/rosette/blending-rosettes/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/rosette/blending-rosettes/"
parent: "/software/ornamental-turning-workbench/rosette/"
---
When there are two or more rosettes placed on a spindle the default action in OTWorkbench is to combine their shapes by taking the maximum radius at each angle between zero and 360 degrees.

<figure class="wp-recovered-caption">
<img alt="No blending present" class="size-full wp-image-288" height="481" src="/assets/placeholder-original-image.svg" title="blend1" width="335"/>
<figcaption>No blending present</figcaption>
</figure>

Blending the rosettes together allows you to make one rosette more influential than the others. You do this by assigning a blending value to each rosette and setting the blend option.

When the blend option is set the overall radius of the rosette at any angle is found by taking the radius of each individual rosette at that angle and multiplying it by the blending value then adding all these together to arrive at a final value. Therefore, blending values &lt;  1.0 will decrease the importance of features on a rosette, whilst blending values &gt; 1.0 will magnify the features of a rosette.

<figure class="wp-recovered-caption">
<img alt="Two rosettes blended together" class="size-full wp-image-291" height="524" src="/assets/placeholder-original-image.svg" title="blend2" width="435"/>
<figcaption>Two rosettes blended together</figcaption>
</figure>

Note that as shown here blending values can be negative as well as positive.

You can blend as many rosettes as there are on the spindle, but note if all bllending values are positive then the final rosette could be quite large.
