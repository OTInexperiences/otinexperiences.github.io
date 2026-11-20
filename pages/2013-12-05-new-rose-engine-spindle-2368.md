---
layout: page
title: New Rose Engine - Spindle
date: 2013-12-05 20:44:13 +0000
author: Alan
categories: []
tags: []
permalink: "/new-rose-engine-spindle/"
original_url: http://ab48.uk/otblog/new-rose-engine-spindle/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/new-rose-engine-spindle/"
---
I am using a spindle that has been manufactured. It can be bought off <a href="http://www.ebay.co.uk/itm/4-Spindle-Upgrade-Real-Bull-Mini-lathe-CJ18-series-/360614326538?pt=UK_Home_Garden_PowerTools_SM&amp;hash=item53f649f10a">eBay</a> and is a replacement spindle for a small mini lathe.

<a href="{{ '/assets/recovered/6b777ea77a-spindle.jpg' | relative_url }}"><img alt="spindle" class="aligncenter size-medium wp-image-2369" height="230" src="{{ '/assets/recovered/25bdd99c52-spindle-300x230.jpg' | relative_url }}" width="300"/></a>
Data
<pre>
Spindle with integral 4"/100mm spindle plate.
72mm register with 84mm PCD, 3mm depth.
The total length is 183.75mm
M27 x 1.5 Thread
T3 taper with 20mm hole all the way through spindle.
6 bolt holes to take either 3 or 4 jaw chucks.</pre>
<h2>Preliminary Design</h2>
I have printed a 30 tooth T5 timing pulley with a key-way and internal diameter of 30.025 mm to fit on spindle . The pulley will take a 25mm wide timing belt.
<p style="text-align: center;"><a href="{{ '/assets/recovered/df90760965-CNC-Parametric-Pulley-v3.png' | relative_url }}"><img alt="T5_PULLEY_30T_30D.png" class="aligncenter wp-image-2432" height="250" src="{{ '/assets/recovered/df90760965-CNC-Parametric-Pulley-v3.png' | relative_url }}" width="328"/></a>The pulley will be connected to a 15 tooth pulley mounted on a stepper motor to give a 2: 1 ratio.</p>
<p style="text-align: center;"><a href="{{ '/assets/recovered/0e3cd94cd7-3-IMG_0043-001.jpg' | relative_url }}"><img alt="3-IMG_0043-001" class="aligncenter wp-image-2425" height="277" src="{{ '/assets/recovered/0e3cd94cd7-3-IMG_0043-001.jpg' | relative_url }}" width="368"/></a></p>
The spindle will run in split Delrin bearings, the front bearing is 30mm diameter and the rear bearing is 28mm diameter. Both bearings have an outside diameter of 35mm and a lip diameter of 40mm and can be held in similar bearing blocks.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/80e5a1e34e-rear-split-bearing-closed.png' | relative_url }}"><img alt="rear-split-bearing-closed" class="size-medium wp-image-2450" height="210" src="{{ '/assets/recovered/000a36d4f8-rear-split-bearing-closed-300x210.png' | relative_url }}" width="300"/></a>
<figcaption>Rear split bearing</figcaption>
</figure>

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/28dd50950b-rear-spindle-block-assembly.png' | relative_url }}"><img alt="Bearing block" class="size-medium wp-image-2449" height="220" src="{{ '/assets/recovered/3215e235fe-rear-spindle-block-assembly-300x220.png' | relative_url }}" width="300"/></a>
<figcaption>Bearing block</figcaption>
</figure>
<h2 style="text-align: left;">Spindle Assembly</h2>
<a href="{{ '/assets/recovered/a874d1e75b-Main-spindle-assembly.png' | relative_url }}"><img alt="Main-spindle-assembly" class="aligncenter size-full wp-image-2447" height="395" src="{{ '/assets/recovered/a874d1e75b-Main-spindle-assembly.png' | relative_url }}" width="713"/></a>This assembly will be fastened to a length of <a href="http://www.robocutters.co.uk/products.asp?cat=Vslot+Aluminium+Profiles">Vslot</a> which is allowed to run along a longer base section of Vslot to give the forwards/backwards pumping movement. In turn the base section will slide transversely along two further Vslot sections. The two transverse Vslot sections will be attached to a simple frame made from standard 20x40 aluminium profile.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/5fbe6f7d39-Main-spindle-assembly1.png' | relative_url }}"><img alt="Drawing of main spindle assembly" class="size-large wp-image-2463" height="330" src="{{ '/assets/recovered/f843a1abd4-Main-spindle-assembly1-1024x529.png' | relative_url }}" width="640"/></a>
<figcaption>Drawing of main spindle assembly</figcaption>
</figure>

There will be a 1 : 2 reduction between the motor and the spindle.
<p style="text-align: left;">The maximum allowable forward movement of the spindle will be limited at 100mm.</p>
 
