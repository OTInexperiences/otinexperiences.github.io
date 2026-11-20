---
layout: page
title: Configuration File
date: 2010-06-14 19:11:49 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/general-introduction/configuration-file/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/general-introduction/configuration-file/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/general-introduction/configuration-file/"
parent: "/software/ornamental-turning-workbench/general-introduction/"
---
The software has a configuration file that allows the user to specify the locations of several folders and the different types of file extensions to be used. NOTE that this file is not included in the tar of the bin folder and has to be updated separately. This allows users to extract files into the bin folder without having to re-edit the configuration file each time.
<p style="text-align: center;"><a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-597 aligncenter" height="518" src="/assets/placeholder-original-image.svg" title="Screenshot-Configuration" width="298"/></a></p>
You can get to this dialog by selecting System &gt; Preferences  from the main menu.  These values are held in an XML  file called<strong> <a href="http://blog.alanbattersby.co.uk/wp-content/uploads/2010/06/OTWorkbench.exe.config.tar.gz">OTWorkbench.exe.config</a></strong> that is stored in the OTWorkbench/bin folder. A typical example for this file is

&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;configuration&gt;&lt;appSettings&gt;
&lt;add key="rootdir" value="/home/alan/OTWorkbench" /&gt;                       <span style="color: #ff0000;">*****Change this value</span>
&lt;add key="bindir" value="bin" /&gt;
&lt;add key="celldir" value="Cell" /&gt;
&lt;add key="latdir" value="Lattice" /&gt;
&lt;add key="gcodedir" value="Gcode" /&gt;
&lt;add key="rosdir" value="Rosettes" /&gt;
&lt;add key="pathdir" value="Paths" /&gt;
&lt;add key="projectdir" value="Projects" /&gt;
&lt;add key="surfacedir" value="Surface" /&gt;
&lt;add key="librarydir" value="Library" /&gt;
&lt;add key="gcodefileextension" value="ngc" /&gt;
&lt;add key="cellfileextension" value="cel" /&gt;
&lt;add key="latfileextension" value="lat" /&gt;
&lt;add key="rosfileextension" value="ros" /&gt;
&lt;add key="spindlefileextension" value="sp" /&gt;
&lt;add key="projectextension" value="info" /&gt;
&lt;add key="surfaceextension" value="surf" /&gt;
&lt;add key="pathextension" value="path" /&gt;
&lt;add key="pathgeneratordataextension" value="dat" /&gt;
&lt;add key="toolFileName" value="Tooltable" /&gt;
&lt;add key="toolfileextension" value="tf" /&gt;
&lt;add key="projectinfofile" value="project" /&gt;
&lt;add key="LastProjectName" value="" /&gt;
&lt;add key="LoadProjectOnStartup" value="True" /&gt;
&lt;add key="ToolDisplayMode" value="QUICKVIEW" /&gt;
&lt;add key="LogFileName" value="log.txt" /&gt;
&lt;/appSettings&gt;&lt;/configuration&gt;

When first setting up OTWorkbench you have at least to change the value of rootdir to reflect your own system. It should be the path to the OTWorkbench folder.
