---
layout: post
title: Netduino Software
date: 2011-02-17 21:41:52 +0000
author: Alan
categories:
- Software
tags: []
permalink: "/blog/netduino-software/"
original_url: http://ab48.uk/otblog/netduino-software/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/netduino-software/"
  - "/otblog/netduino-software/"
---
Well, I have started to play around with the Netduino Plus (N+). There is so much to learn!!. So far I have a small demo application that displays information on the small screen attached to my N+ . There is a socket connection so that a program running on the pc can send information to the N+ over the network.  Not much really but in order to get this far I had to
<ul>
<li>Find out how to talk to and control the screen.</li>
<li>Re-learn stuff I had forgotten about how to use sockets.</li>
<li>Understand how to generate user events on the N+</li>
</ul>
Fortunately there is a lot of help in the Netduino forums, there needs to be as there is not yet much documentation available.

Next phase is to extend my tiny demo to being able to download a file from the pc onto the N+ 's SD card. When I can do that I can use it to transfer the Rosette data onto the N+ in order to control the stepper motors of my Rose Engine.
