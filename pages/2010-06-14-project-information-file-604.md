---
layout: page
title: Project Information File
date: 2010-06-14 20:15:42 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/general-introduction/project-information-file/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/general-introduction/project-information-file/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/general-introduction/project-information-file/"
parent: "/software/ornamental-turning-workbench/general-introduction/"
---
Every project has its own information file that by default (you havent changed the standard configuration) is called project.info.

When a new project is created then a file called default_project_settings.info is copied into the project folder and renamed as project.info.

You can create or alter the default settings by selecting System &gt; Default Project Settings from the main menu
<p style="text-align: center;"><a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-605 aligncenter" height="86" src="/assets/placeholder-original-image.svg" title="default_project_info1" width="226"/></a></p>
<p style="text-align: left;">This will create a new project information file and edit it using the project information dialog.</p>
<p style="text-align: left;">To change the project settings associated with the project currently open click the button labelled information which lies on the right hand side of the status bar at the bottom of the main window.</p>
<h3 style="text-align: left;">Project Information Window</h3>
<p style="text-align: left;">There are many settings you can alter, so they are collected into several categories.</p>
<ul>
<li>General</li>
<li>Axes</li>
<li>Machining Data</li>
<li>Tool Box</li>
<li>Surface</li>
<li>Data</li>
<li>Display</li>
</ul>
<h4>The General options allow you to</h4>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-606" height="326" src="/assets/placeholder-original-image.svg" title="Project Information Dialog1" width="430"/></a>
<figcaption>General options</figcaption>
</figure>
<ol>
<li>Change the Accuracy which is the number of decimal places to work to.</li>
<li>Specify the type of G code to be produced.</li>
<li>Say if during a repeat run the original tool position should be restored at the end of that run</li>
<li>Specify if the current Path Executor should run automatically just after the project is loaded.</li>
<li>Specify if all existing paths should be saved as the current project is closed.</li>
<li>Set the scale increment and radial increment values for the grid.</li>
<li>Set the maximum radial value for the grid.</li>
<li>Make a few textual notes about the project as a memory aid.</li>
</ol>
<p style="text-align: left;"></p>
<p style="text-align: left;"></p>
<p style="text-align: left;"></p>


<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-607" height="326" src="/assets/placeholder-original-image.svg" title="Project Information Dialog2" width="430"/></a>
<figcaption>Axes options</figcaption>
</figure>
<h4 style="text-align: left;"></h4>
<h4 style="text-align: left;"></h4>
<h4 style="text-align: left;"></h4>
<h4 style="text-align: left;"></h4>
<h4 style="text-align: left;"></h4>
<h4 style="text-align: left;">The Axes options allow you to</h4>
<ol>
<li>Specify if you are using a rotatory table. Note that a standard Roselathe such as the one I build can be considered to be a large rotary table.</li>
<li>Specify the machine axes.</li>
<li>State which CNC axes will be used.</li>
</ol>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-608" height="326" src="/assets/placeholder-original-image.svg" title="Project Information Dialog3" width="430"/></a>
<figcaption>Machining options</figcaption>
</figure>
<h4></h4>
<h4></h4>
<h4></h4>
<h4></h4>
<h4></h4>
<h4>Machining Data</h4>
Here you can specify
<ol>
<li>The units used</li>
<li>The depth of a roughing cut</li>
<li>The depth of a finishing cut</li>
<li>The linear feed rate</li>
<li>The angular feed rate</li>
<li>The tool overlap between each width pass when cutting a path wider than the current tool.</li>
<li>The safe height to move too at the end of a path.</li>
<li>A flag to set the depth direction to be along the negative axis.</li>
<li>The depth of the nominal surface if a surface file is not in use.</li>
</ol>
<h4></h4>
<h4></h4>
<h4></h4>
<h4><a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-609 alignright" height="326" src="/assets/placeholder-original-image.svg" title="Project Information Dialog4" width="430"/></a></h4>
<h4></h4>
<h4></h4>
<h4>Tool Box</h4>
Here you can specify names of tools and their diameters and lengths.
<h4></h4>
<h4></h4>
<h4></h4>
<h4></h4>
<h4>Surface</h4>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-610" height="326" src="/assets/placeholder-original-image.svg" title="Project Information Dialog5" width="430"/></a>
<figcaption>Surface information</figcaption>
</figure>

Here you can give the name of a file representing the surface to be used in the project. If you wish to use a surface you must also set the Use a surface option. Furthermore you can tell OTWB if it is to follow the surface contours when generating and cutting a path. And finally if the surface on which you are cutting is already pre-machined to its final shape. If you do not set this final switch OTWB will assume that the depth to cut will be starting at the nominal surface depth (usually zero) and will then generate the required number of depth passes to reach that depth. If the final switch is set OTWB will assume that it can do a fast feed down to the  surface depth before its starts a cut.
<h4></h4>
<h4></h4>
<h4></h4>
<h4></h4>
<h4></h4>
<h4>Data</h4>
<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-611" height="326" src="/assets/placeholder-original-image.svg" title="Project Information Dialog6" width="430"/></a>
<figcaption>Miscellaneous values</figcaption>
</figure>

This category holds various miscellaneous values
<ol>
<li>The name of the headstock file.</li>
<li>The name of the script executor (not yet implemented)</li>
<li>A flag to show if using an index plate instead of specifying angles in degrees.</li>
<li>The chuck display</li>
<li>Default values for Angle increment and Radius to be used when creating a Rosette by specifying points.</li>
<li>A flag to set the assumption that newly created paths are closed.</li>
<li>Tow values to specify the blending range for Rosettes.</li>
<li>A list of lattices to be loaded into the system.</li>
</ol>
<h4></h4>
<h4></h4>
<h4></h4>
<h4></h4>
<h4>Display Values</h4>
Various clolour values to be used by the path displays. see <a href="{{ '/software/ornamental-turning-workbench/rose-engine-project-2/tool-path-display/' | relative_url }}" target="_self">tool-path-display</a>
