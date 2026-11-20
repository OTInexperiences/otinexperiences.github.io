---
layout: page
title: Tool Path Display
date: 2010-06-09 16:27:42 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/rose-engine-project-2/tool-path-display/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/rose-engine-project-2/tool-path-display/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/rose-engine-project-2/tool-path-display/"
parent: "/software/ornamental-turning-workbench/rose-engine-project-2/"
---
The tool path display gives  a colour coded view of the paths created for the current project.  These paths are stored in a structure called the Model so the tool path display gives you a graphical view of the model.
<h3>Types of Display</h3>
There are two types of display a full three dimensional view and an alternative two dimensional view looking down the Z axis.Unfortunately due to problems with the current 3D graphica package used the 3D display is currently unuseable.
<h4>Quickview - the 2D display</h4>
The quickview display can be customised by changing several values in the project information file. You can choose

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-590" height="326" src="/assets/placeholder-original-image.svg" title="toolpathdisplay3" width="430"/></a>
<figcaption>Customiseable choices for the path display</figcaption>
</figure>
<ul>
<li>The path colour</li>
<li>The background colour</li>
<li>The highlight colour</li>
<li>The colour of the grid which is the Front face colour</li>
<li>The Visible point colour</li>
<li>The Hidden point colour</li>
<li>The up point colour</li>
<li>The Down point colour</li>
<li>The Fill area colour</li>
<li>The Mask area colour</li>
<li>The area transparency.</li>
<li>The colour for action points</li>
<li>A boolean flag to show hidden sections of path as a dashed line.</li>
<li>A flag if true will display the Up and Down boundary points in their defined colours.</li>
</ul>
There are several buttons along the bottom of the display

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-589" height="585" src="/assets/placeholder-original-image.svg" title="toolpathdisplay" width="498"/></a>
<figcaption>Quickview path display</figcaption>
</figure>
<ul>
<li>The first button <a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-591 alignnone" height="38" src="/assets/placeholder-original-image.svg" title="toolpathbtn1" width="43"/></a> will cause the points along a path to be displayed.</li>
<li>The next two buttons are for swapping the display view. At present they do nothing as this facility has not yet been implemented.</li>
<li>The third button <a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-592 alignnone" height="38" src="/assets/placeholder-original-image.svg" title="toolpathbtn4" width="36"/></a> will hide or show the grid.</li>
<li>The fourth button will remove all paths from the model.</li>
<li>The fifth button will home the display so that the Z axis is at the centre of the display and the scale is set so that the grid just fits the display size.</li>
</ul>
Also there are three information fields showing; the current scale, the offset from centre and ???

You can drag the display around by holding down the left mouse button but you cannot as yet select an individual path.

If you hold down the right mouse button and drag, you will define a rectangle which will become the current view area. This enables you to zoom in on individual features etc.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-593" height="576" src="/assets/placeholder-original-image.svg" title="toolpath6" width="845"/></a>
<figcaption>Dragging the mouse whilst holding down the right button selects an area to display</figcaption>
</figure>
