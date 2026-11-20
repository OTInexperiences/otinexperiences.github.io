---
layout: page
title: Model Explorer
date: 2009-08-15 17:50:38 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/rose-engine-project-2/model-explorer/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/rose-engine-project-2/model-explorer/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/rose-engine-project-2/model-explorer/"
parent: "/software/ornamental-turning-workbench/rose-engine-project-2/"
---
The model explorer allows you to view all paths, their properties and vertices  in the model.

From left to right the buttons along the upermost button bar allow you to
<ol>
<li>Remove all paths from the model.</li>
<li>Remove only those paths that are neither a guide nor an area.</li>
<li>Mark all paths in the model for inclusion. These paths are displayed  and contribute to G code generation.</li>
<li>Mark all paths in the model for exclusion. These paths will not be included for display or  G code generation.</li>
<li>Remove all marking artifacts making all points visible.  Note segmented paths cannot be restored.</li>
<li>Apply all selected areas to all selected paths in the model.</li>
<li>Snip all paths in model that are neither areas nor marked as guides.</li>
<li>Export selected paths to the Library.</li>
<li>Import paths selected from the Library.</li>
<li>Save all selected paths to the project folder.</li>
<li>Open paths selected from the project folder.</li>
</ol>
<a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-full wp-image-675" height="970" src="/assets/placeholder-original-image.svg" title="model-explorer1" width="431"/></a>

The five buttons along the middle button bar allow you to
<ol>
<li>Hide all non included paths from being displayed in the path explorer. Note no icon for this yet.</li>
<li>Give information about the extent of the paths in the model.</li>
<li>Generate a polygonal area without using the headstock.</li>
<li>Generate a circular area without using the headstock.</li>
<li>Generate a rectangular area without using the headstock.</li>
</ol>
The bottom half of the panel is a <a href="http://blog.alanbattersby.co.uk/ornamental-turning-workbench/rose-engine-project-2/vertex-explorer/" target="_self">vertex explorer</a>.

The mode explorer has a pop-up menu that appears when you select one or more paths and click the right mouse button.

<a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-full wp-image-685" height="290" src="/assets/placeholder-original-image.svg" title="model-explorer-popup" width="426"/></a>

The options on that menu apply to paths and allow you to
<ul>
<li>Create and apply a Transform or remove all transforms.</li>
<li>Create a path reference.</li>
<li>De - reference a path.</li>
<li>Group paths together.</li>
<li>Apply an operator to a path.</li>
<li>Create an area or add an inner boundary.</li>
</ul>
Furthermore a path such as an area or reference can itself refer to other paths. You can inspect these other paths by expanding the tree node for the root path.

<a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-full wp-image-686" height="156" src="/assets/placeholder-original-image.svg" title="model-explorer3" width="474"/></a>

In the image above Path_1 is a simple path with no other constituents. Path_2 is a reference so has a constituent path but the root (ie Path_2) has not been expanded. Whilst Path_3 also a path reference has been expanded to allow us to inspect its constituent, which shows us that Path_3 is a reference to Path_1.
