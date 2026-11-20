---
layout: page
title: Action Points and Action Blocks
date: 2010-06-05 19:10:53 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/paths/action-points-and-action-blocks/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/paths/action-points-and-action-blocks/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/paths/action-points-and-action-blocks/"
parent: "/software/ornamental-turning-workbench/paths/"
---
<h3>Action Points</h3>
Each vertex may be designated an action point which  is a point at which some designated action is to occur.
<div><dl id="attachment_489"> <dt><a href="/assets/placeholder-original-image.svg"><img alt="" height="260" src="/assets/placeholder-original-image.svg" title="path7" width="635"/></a></dt> <dd>Action point is hilighted in purple</dd> </dl></div>
These actions are represented by ActionBlocks which define the action and also hold any further required parameters.
<h3>Creating Action Points</h3>
Action points may be assigned to path vertices manually by selecting the vertex in the vertex explorer, right click to show the menu and then selecting Add Action Point. You can also use this menu to remove an action point or to remove all action points.

<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-552" height="193" src="/assets/placeholder-original-image.svg" title="actionpoint2" width="501"/></a>

Another way to create action points is through the use of an action rule.  Currently there are four action rules. The first two rules are Index rules as they depend upon the vertexes position in the path whilst rules 3 and 4 are vertex rules as they require data based on the vertex itself.

The rules are
<ol>
<li>Make every vertex an action point.</li>
<li>Make every Nth vertex an action point.</li>
<li>Make an action point at every N degrees.</li>
<li>Make N action points at equally spaced positions around the path.</li>
</ol>
To apply an action rule select your path in the paths explorer, right click and choose theAction Rule sub menu

<a href="/assets/placeholder-original-image.svg"><img alt="" class="alignnone size-full wp-image-553" height="248" src="/assets/placeholder-original-image.svg" title="actionpoint3" width="644"/></a>

Then choose Create rule and the rule will be applied after you have filled in the relevant information such as the value of N for an every N type rule.

You can also use the Action rule sub menu to edit a rule, re apply a rule , or remove a rule.

Note that when you create an every N rule the default value of N is set to 1. You must then change this to the  value you want and re-apply the rule.

<figure class="wp-recovered-caption">
<a href="/assets/placeholder-original-image.svg"><img alt="" class="size-full wp-image-556" height="414" src="/assets/placeholder-original-image.svg" title="actionpoint4" width="426"/></a>
<figcaption>On this circle the rule is Every 20</figcaption>
</figure>
<h3>Action Blocks</h3>
Examples of action blocks  will be
<ol>
<li>Either drill or plunge a cutter to a given depth. To be able to drill/mill a pattern of holes</li>
<li>Place an area at this point. To easily place several copies of an area at positions along the path see <a href="http://blog.alanbattersby.co.uk/ornamental-turning-workbench/paths/using-area-action-blocks/" target="_self">clock face</a> example</li>
<li>Cut another path centered at this point. To cut paths around another path.</li>
<li>Cut a pocket using another path as its boundary at this point.</li>
</ol>
Currently only the Area action block is implemented.
