---
layout: page
title: Development History
date: 2009-09-06 17:28:32 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/software-download/development/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/software-download/development/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/software-download/development/"
parent: "/software/ornamental-turning-workbench/software-download/"
---
<h4>Changes 8 June 2010</h4>
<ul>
<li>Allowed projects folder to contain sub folders.</li>
<li>Changed structure of paths so that each point has a state that is either VISIBLE (V) , HIDDEN (H), UP(U) or DOWN(D)</li>
<li>Paths may be segmented and segments marked by DOWN and UP  which act as instructions to lower or raise the cutter from / to the safe height.</li>
<li>Mask has been replaced by<strong> Area</strong>. An area has one exterior boundary but can have zero or more interior boundaries. Interior boundaries are holes in the area.</li>
<li>Points are labeled as a result of applying an area to a path.  If the area is a MASK then any point on a path lying within the area is marked as HIDDEN points outside the area are marked as VISIBLE and the boundary points where the path enters or leaves the area are created and marked UP or DOWN accordingly.  If the area is marked FILL the opposite occurs, any point inside the area is marked as VISIBLE whilst those outside are marked HIDDEN.</li>
<li>You can have multiple areas but they must all be of the same type, either all FILL or all MASK.</li>
<li>There is now a Snip function that will permanently remove any HIDDEN  points from the path.</li>
<li>Virtual items have been replaced by a <strong>Path Reference</strong>.  You can make a reference to a path or an area or another reference.</li>
<li>References to Areas behave just like a standard area.</li>
<li>Guides have been removed now any path that is not already area can have its points labeled as <strong>Action Points</strong>. You can then add one or more <strong>Action Blocks</strong> to the path. When an action point is encountered the action described by the action blocks is performed.</li>
<li>Currently only<strong> Area Action Blocks</strong> are fully defined.</li>
<li>Area action blocks allow the user to place an area at every action point on the path. All area action blocks attached to a path must be of the same type of Area. A path with an area action block and active action points is considered to be an area and can be used just as standard areas.</li>
<li>Action points my be assigned to a path either  manually using the vertex explorer popup menu, or by applying an <strong>Action Rule</strong>. Current action rules are;  All points, Every Nth point, Every N degrees and N points equally spaced along the path. In all cases N is a parameter to be specified.</li>
<li>Several path operations have been defined these are; <strong>Refine</strong> which adds points to a path, and  <strong>Coarsen</strong> which removes points from a path,<strong> UnRef </strong>which takes a reference and flattens it into a new path and<strong> Snip </strong>which removes all hidden points and segments the path.</li>
<li>G code generators changed to reflect changes in path structure.</li>
<li>Button added to G code generator panel to generate separate g code  files one, for each included path as well as the button to generate a single file containing g code for all paths.</li>
<li>Changes to project information file to allow user to specify colors used in quick-view and other values.</li>
<li>NOTE due to problems with OpenGL package used the 3D display window will still cause program to crash so do not choose that option in system default file.</li>
</ul>
<h4>Changes 5 March 2010</h4>
<ul>
<li>Fixed polygon masks.</li>
<li>Added default project file.</li>
<li>Note that in fixing polygon paths I have broken guide paths so that you cannot make a polygon path a guide.</li>
</ul>
<h4>Changes 24 Jan 2010</h4>
<ul>
<li>Fixed to generate paths for pattern3</li>
</ul>
<h4>Changes 12 Jan 2010</h4>
<ul>
<li>Allow scrolling of paths in path explorer</li>
<li>Fix crash when crashes in virtual non selection</li>
<li>Allow negative coords for cartesian translation</li>
<li>Fix non feed to depth problem in gcode generation in absolute mode</li>
</ul>
<h4>Changes 9 Jan 2010</h4>
<ul>
<li>First implementation of masking paths</li>
</ul>
<h4>Changes 1 December 2009</h4>
<ul>
<li>Updated to use latest version of <a href="http://www.opentk.com/">OpenTK</a></li>
<li>Changed to using a unified project file.</li>
<li>Changed the model explorer.</li>
<li>Expanded the Property Explorer</li>
<li>Added different types of path including masks.</li>
<li>Added path transformations. To access this and the previous point right click in the model explorer and use the menu options.</li>
</ul>
Note that the lattice stuff still doesnt work.

Yet to do
<ul>
<li>Implement path masking in quickview and g code generation.</li>
<li>Add path editing to quickview</li>
<li>Change the 3D view so it works with the latest version of opentk.</li>
<li>generate paths for lattice cells.</li>
</ul>
<h4>Changes 31 October 2009</h4>
<ul>
<li>Fixed bug that crashed program if name of project in project info was different from name of project folder.</li>
<li>Fixed bug in indexing</li>
</ul>
<h4>Changes 30 October 2009</h4>
<ul>
<li>Reduced UI  and re-arranged size to fit 1024 x 768.  <strong>NOTE</strong> You can drag panels out of main to undock them, then resize to your requirement.</li>
<li>Removed toolbar on main page and placed functionality in two menu items.</li>
</ul>
<h4>Changes 26 October</h4>
<ul>
<li>Changed maximum frequency of Sinusoid rosette to be 200.</li>
<li>Changed Sinusoid Rosette to optionally allow absolute (positive) values only if wanted.</li>
<li>Allowed optional spindle indexing. You can specify the number of holes in the spindle plate.</li>
<li>Introduced blending between two or more Rosettes as an option. Standard weighting values are user defined in project info</li>
<li>Changed   Spindle UI so both phase and blending values can be altered in the list box. Click on a field in the box and you will be presented with a spin button allowing a value to be selected.</li>
</ul>
<h4>Changes 26 September</h4>
<ul>
<li>Changed so tool depth movement can be negative</li>
<li>Incorporated repeater data into project info so no longer a file on its own</li>
<li>Altered typo on Gcode save.</li>
<li>Changed from G93 inverse time to G94 Units per minute</li>
<li>Added initial stab at profiled rosette but creating and editing is crap.</li>
<li>I have changed the quickview display to more accurate. Added a quick scale changer to save mouse wheel scrolls</li>
<li>Empty project can be saved under a standard name.</li>
<li>Tool position at end of repeat can either be the original position before the repeat or the final position after the repeat. This is governed by a flag called Retain_Original_tool_Position which if set true restores the original position.</li>
</ul>
<h4>Known bugs</h4>
