---
layout: page
title: Software Download
date: 2009-07-03 14:39:05 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/software-download/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/software-download/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/software-download/"
parent: "/software/ornamental-turning-workbench/"
---
My software is written in c# and runs under mono on Opensuse 11.2. It also works ok with Ubuntu 8.04. If you wish to run this software you will first have to install the latest version of <a href="http://www.mono-project.com/Main_Page">mono</a>.

My code assumes the following folder structure

<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-464" height="391" src="/assets/placeholder-original-image.svg" title="folders" width="511"/></a>

The Root folder is OTWorkbench,
<ul>
<li>the bin folder holds the code,</li>
<li>the Library folder holds items to be saved and used on a cross project basis,</li>
<li>the Projects folder holds individual projects.</li>
</ul>
The file default_project_settings.info is an XML file that allows you to set common project settings.

The log file logXXXX.txt is not fully used yet but records the results of any exceptions that cause the project to crash. (Yes sorry folks it still does that)

There is also shell code to start the program called OTWorkbench.sh

This tar <a href="http://www.otinexperiences.co.uk/wp-content/uploads/2010/06/OTWorkbench_Linux_Bin-08-June-2010.tar.gz">OTWorkbench_Linux_Bin-08-June-2010.tar.gz</a> is simply the binary executables that are placed in the bin folder.

If you make changes to the folder structure you must reflect those changes in the file OTWorkbench.exe.config which is found in the bin folder.
<h3>Some sample Projects</h3>
<a href="http://www.otinexperiences.co.uk/wp-content/uploads/2010/06/Projects.tar.gz">Projects.tar.gz</a>

Thanks for your interest.

Alan
