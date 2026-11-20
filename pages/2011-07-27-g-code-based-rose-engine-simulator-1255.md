---
layout: page
title: G Code based Rose engine simulator
date: 2011-07-27 15:41:19 +0000
author: Alan
categories: []
tags: []
permalink: "/software/g-code-examples/g-code-based-rose-engine-simulator/"
original_url: http://ab48.uk/otblog/software/g-code-examples/g-code-based-rose-engine-simulator/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/g-code-examples/g-code-based-rose-engine-simulator/"
parent: "/software/g-code-examples/"
---
A week or so ago whilst writing my universal program that made use of emc’s user variable are I thought about the possibility of writing a rose engine simulator entirely in g code. I started writing this program as an experiment and it is ongoing. Whilst not being complete I think it is a useable program. Though of course its major drawback is that it does not have a user interface so everything is textual.

Well after a little bit of work I here is the result. It is a fairly simple program that could be extended further if someone wanted to. For want of a better name I will call it GRose. I would be interested in any feedback or the results of any development work you may undertake.
<pre>This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    see &lt;http://www.gnu.org/licenses/&gt; for a copy of the GNU General Public License.</pre>
<ol>
<li>Explanation and <a href="{{ '/grose-user-guide/' | relative_url }}" title="RoseG User Guide">short user guide</a> explaining the background and functionality</li>
<li><a href="{{ '/assets/recovered/0c2cd40034-GRose.pdf' | relative_url }}">Documentation</a></li>
<li><a href="{{ '/software/g-code-examples/g-code-based-rose-engine-simulator/grose-examples/' | relative_url }}" target="_blank" title="GRose Examples">Examples</a></li>
<li>The current versions of the program called <a href=" https://github.com/alanbattersby/Gcode_programs">grose_v2_XYZ </a> Please copy and save as roseg.ngc to use with emc.</li>
</ol>
grose_v2_XYZ is intended to be used on a standard mill whose table moves in XY and depth is Z.

 
