---
layout: page
title: New Rose Engine - Electronics
date: 2013-12-05 21:33:13 +0000
author: Alan
categories: []
tags: []
permalink: "/new-rose-engine-electronics/"
original_url: http://ab48.uk/otblog/new-rose-engine-electronics/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/new-rose-engine-electronics/"
---
Thanks to some timely correspondence with Jon Magill I have decided to opt for the Arduino <a href="http://uk.farnell.com/arduino/a000062/at91sam3x8e-arduino-due-dev-board/dp/2250861">Due</a> processor running a <a href="https://www.synthetos.com/project/grblshield/">grblSheild</a> to control the motors.

Each motor will be fed a series of pulses from a stepper/servo driver. There will be a reference stream running at a high frequency. In turn each motor will be fed from a slower stream obtained from the reference stream by division.

<a href="{{ '/assets/recovered/01f4a72374-dividers.png' | relative_url }}"><img alt="dividers" class="aligncenter size-full wp-image-2376" height="354" src="{{ '/assets/recovered/01f4a72374-dividers.png' | relative_url }}" width="639"/></a>

I still have not made a decision how this will happen. I could write my own code from scratch or use an existing library like the TinyG library further investigation is needed.

 

 
