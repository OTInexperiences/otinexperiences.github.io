---
layout: page
title: OTWB Windows 8 App
date: 2013-02-17 16:09:20 +0000
author: Alan
categories: []
tags: []
permalink: "/otwb-windows-8-app/"
original_url: http://ab48.uk/otblog/otwb-windows-8-app/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/otwb-windows-8-app/"
---
This is the root page describing my Windows App version of OTWB software. This program is used to generate several different types of patterns and then produce the g-code program to allow those patterns to be cut on a cnc system such as the one I have described in this blog.

<figure class="wp-recovered-caption">
<a href="{{ '/assets/recovered/8397a216d1-FrontPage.png' | relative_url }}"><img alt="App start page" class="size-medium wp-image-2087" height="170" src="{{ '/assets/recovered/1055ca8077-FrontPage-300x170.png' | relative_url }}" width="300"/></a>
<figcaption>App start page</figcaption>
</figure>
<h2>Path Sources</h2>
You can generate simple paths from 4 sources each in the XY plane.
<ol>
<li>A simulated Bazley Chuck that produces examples based on the values given in his book<a href="{{ '/bazley-chuck-page/' | relative_url }}" title="App Bazley Chuck Page"> see here</a>.</li>
<li>Patterns described by <a href="http://openlibrary.org/books/OL2752300M/Microcomputer_art">Ross</a> in his book<a href="{{ '/app-ross-page/' | relative_url }}" title="App Ross Page"> see here</a>.</li>
<li>Patterns described by “Wheels on Wheels on Wheels—Surprising Symmetry,” Mathematics Magazine 69(3), 1996 pp. 185–189 by F. A. Farris. <a href="{{ '/app-wheels-page/' | relative_url }}" title="App Wheels Page">See here</a> and also <a href="http://www.walkingrandomly.com/?p=1471" target="_blank">this site</a> for more information.</li>
<li>Paths described by a barrel of a rose engine <a href="{{ '/app-rose-page/' | relative_url }}" title="App Rose page">see here</a>.</li>
</ol>
<h2>A Template driven approach</h2>
To use this program efficiently you need to know something about g-code. This is because I generate the g-code from a series of textual templates that the user has to specify. I have decided to go in this direction because, in previous versions  the c# code I had to write to produce the actual g-code was becoming ever more complex as I tried to take account of different ways of working. In this version, I am leaving this complexity to the user so if you as the user want to do a specific task you have to write the templates to accomplish that. (Please note that this approach is very much at the beginning of its development. As time allows I will try to produce differing sets of templates. See the documentation <a href="{{ '/assets/downloads/OTWBHelp.pdf' | relative_url }}">here</a> for more information

Finally I chose the windows 8 App because 1) I wanted to have a go at writing one and 2) I like the uncluttered user interface. So gone are the multiple frames and instead you navigate to different windows (each of which occupies the whole screen).

There are many bits that need finishing see my <a href="{{ '/otwb-windows-8-app-todo-list/' | relative_url }}" title="OTWB Windows 8 App TODO List">TODO</a> list.

 

 

 
