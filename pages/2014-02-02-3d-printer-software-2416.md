---
layout: page
title: 3D Printer Software
date: 2014-02-02 22:56:34 +0000
author: Alan
categories: []
tags: []
permalink: "/3d-printer-software/"
original_url: http://ab48.uk/otblog/3d-printer-software/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/3d-printer-software/"
---
You need several programs to design and print stuff.

Firstly you need a design (CAD) program in order to create your part. The one I am currently using is free and is called <a href="http://www.designspark.com/eng/page/mechanical">DesignSpark Mechanical</a> provided by RS components. There is also another useful program called <a href="http://www.openscad.org/">OpenScad</a> which takes a programming view of creating parts. There are many other programs you could use some free and some commercial.  Many designs for parts are freely available on a website called  <a href="http://www.thingiverse.com/">thingverse</a>.

After you have designed your part you need to create a file of instructions to be sent to the printer to enable it to create the part. This complex task is achieved using a translation program . I am using another freely available program called<a href="http://slic3r.org/"> slic3R </a>for this task.

Finally you need a program to control your printer. To set up the printer and to send the gcode file created in the previous step to it. I am currently using a program called pronterface to control my printer using a serial port through a usb cable connecting my printer to my PC. RepRapPro provide a version for their Ormerod printer <a href="https://github.com/reprappro/Software/">here</a>.
