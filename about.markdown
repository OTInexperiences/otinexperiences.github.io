---
layout: "page"
title: About this blog
date: 2008-08-19 08:02:46 +0000
author: Alan
categories: []
tags: []
permalink: "/about/"
original_url: http://ab48.uk/otblog/about-2/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/about-2/"
  - "/otblog/about-2/"
---
This site reflects my interest in Ornamental Turning (OT) , Mathematics  particularly geometry and computer programming. I have built a Rose engine that uses stepper motors and software to control the motion of the headstock instead of the traditional rosettes. In fact I am using  software rosettes generated using a designer I am writing called OTWorkbench. This designer which is a simulation of a rose engine allows me to generate Gcode that defines the movement of the headstock. I use a free piece of software called <a href="http://linuxcnc.org/" target="_self"> Emc</a> to actually control the stepper motors.


<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/bbcc75c0d2-IMG_0068.jpg' | relative_url }}"><img alt="" class="size-large wp-image-899" height="473" src="{{ '/assets/recovered/056df7c839-IMG_0068-1024x757.jpg' | relative_url }}" title="IMG_0068" width="640"/></a>
<figcaption>Rose engine setup</figcaption>
</figure>

The picture above shows the finished machine together with its overhead drive in my new work area dedicated to its use.
<p style="text-align: left;">I started using a <a href="http://www.proxxon-direct.com/acatalog/Mill_Drill_system_BFW_40_E_with_controller.html" target="_blank">Proxxon</a> milling head to cut paths in my bowls, now I have build a more traditional cutting frame and drilling spindle which are connected by poly belting to a 1/2 hp three phase variable speed motor via a overhead drive (see main picture above)</p>
<p style="text-align: left;">To give you some idea of scale, the bowl shown above is 14 inches (~360mm) in diameter. I have altered the machine by raising the spindle height so that now I can hold a piece of work that is 18 inches (450mm)  in diameter, the same as my wood lathe and by judicious placing of the cutting head can cut anywhere on that surface . The machine also has a pumping capacity (the ability of the headstock to move forwards) of just under 6 inches (150mm) which is the same as the tool post maximum reach.</p>
<p style="text-align: left;">The bed bars are 700mm long and are in fact a bit too short so I need to replace them with bars 1000mm long.</p>
<p style="text-align: left;">I started building the machine above in September 2009 and it has taken about 12+ months of machining Aluminum not wood to create the rose engine and about another 8 months to finish the toolpost, overhead, cutting frames, polisher workshop extension to hold this equipment etc. (No work between November 2010 and February 2011 as winter too cold in workshop).</p>
<p style="text-align: left;">Thus this machine has 4 axes of movement which are</p>
<ol>
<li>Rotation around the main spindle using stepper motor set in half step mode connected to the main spindle through a 16:1 gearbox giving a rotation of 0.05625 degrees per step.</li>
<li>Linear movement along the main spindle (for pumping) using stepper motor in half step mode connected to ball screw of 5mm pitch giving 0.0125mm per step</li>
<li>Linear movement at 90 degrees to the main spindle (rose simulation) In the horizontal plane through the centre of the main spindle using stepper motor in half step mode connected to a ball screw of 5mm pitch giving 0.0125mm per step.</li>
<li>Linear movement in direction of cutter which can be set at any angle in the horizontal plane through the centre of the main spindle by rotating the tool post. Using a stepper motor in half step mode connected to an acme screw of 3mm pitch giving 0.0075mm per step.</li>
</ol>
<a href="{{ '/assets/recovered/Directions-labelled-150x150.png' | relative_url }}"><img alt="Directions of movement, labelled X, Y, B and V" class="alignnone wp-image-939" height="150" src="{{ '/assets/recovered/Directions-labelled-150x150.png' | relative_url }}" title="Directions" width="150"/></a>