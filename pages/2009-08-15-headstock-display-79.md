---
layout: page
title: Headstock Display
date: 2009-08-15 17:48:01 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/rose-engine-project-2/headstock-display/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/rose-engine-project-2/headstock-display/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/rose-engine-project-2/headstock-display/"
parent: "/software/ornamental-turning-workbench/rose-engine-project-2/"
---
The headstock is the major component of a rose engine. Its sliding/rocking movement moves the work towards or away from the cutting tool allowing complex outlines to be cut.  The headstock movement is controlled by several factors such as the number,type and phase of the Rosettes placed on its spindle and the position and type of the rubber used. My software allows the user to add / remove different Rosettes to the spindle, alter the phase of a rosette and alter the position of the rubber but not its outline.
<a href="{{ '/assets/recovered/a3a46430da-headstock.png' | relative_url }}"><img alt="" class="alignnone size-medium wp-image-355" height="300" src="{{ '/assets/recovered/3a6afb17d6-headstock-207x300.png' | relative_url }}" title="headstock" width="207"/></a>

The interface is divided into several parts

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-359" height="251" src="/assets/placeholder-original-image.svg" title="toparea" width="300"/></a>
<figcaption>Main spindle / Squash  spindle Editor</figcaption>
</figure>

The spindle editor allows you to edit or change the number and types of rosettes on a spindle. An icon shows the outline of each individual rosette. The other items shown are the value of the current Phase of the rosette together with  any Blending value and if the Rosette is to be included on the spindle. The Phase and Blending values can be changed by clicking on the text field and entering a new value. A Rosette is excluded by simply unchecking the checkbox. Options in the button bar allow you to edit a rosette, add a new rosette, remove a selected rosette and save a selected rosette in the library.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-358" height="216" src="/assets/placeholder-original-image.svg" title="spindle-outline" width="300"/></a>
<figcaption>Spindle Outline</figcaption>
</figure>

The middle area shows the combined outline of the rosettes currently on the  spindle taking into account any blending. You can zoom in and out of this image by moving the mouse scroll button and pan left and right by holding down the left mouse button and moving the mouse.  The dotted circle shows the mean radius of the combined rosettes and that is the position of the rubber which is marked by the blue triangle. The turns button allows you to specify the number of full rotations to view, the default is 1. Although not plotted the values of the maximum and minimum radii are shown below the image.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-360" height="117" src="/assets/placeholder-original-image.svg" title="spindle-data" width="300"/></a>
<figcaption>Spindle Information</figcaption>
</figure>

The lower area shows other spindle information such as the type of engine default LINEAR and gives a count of the number of Rosettes on the spindle. The Phase of a rosette can also be changed by first selecting the rosette and then adjusting the value in the phase spinbutton. There is a check box to set if the spindle is to be indexed and if so specify the number of holes in the index plate.  Also a checkbox to specify if the rosettes are to be blended together. If so then the blending values are used to weight the importance of each rosette. There are also check boxes to specify which axis the spindle controls X, Y or Z or any combination. Finally there are two buttons to position the rubber at either the left or right hand side of the spindle. The actual value is for information only and cannot be used to change the rubber position which is always at the mean radial position.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-medium wp-image-363" height="39" src="/assets/placeholder-original-image.svg" title="chuck-info" width="300"/></a>
<figcaption>Chuck Information</figcaption>
</figure>

Finally there is a way to define and edit the chuck used on the spindle via  the information button. Clicking this button will open a dialog to define various chuck parameters <a href="http://blog.alanbattersby.co.uk/ornamental-turning-workbench/project-information/chuck/" target="_self">see further data on chuck</a>.
