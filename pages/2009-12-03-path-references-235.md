---
layout: page
title: Path References
date: 2009-12-03 00:26:24 +0000
author: Alan
categories: []
tags: []
permalink: "/software/ornamental-turning-workbench/paths/path-references/"
original_url: http://ab48.uk/otblog/software/ornamental-turning-workbench/paths/path-references/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/software/ornamental-turning-workbench/paths/path-references/"
parent: "/software/ornamental-turning-workbench/paths/"
---
Path references are a way of applying a path transformation to another path without copying that paths vertex list. The path reference has no physical vertices of its own instead it is linked to another path.  The points on a path reference are generated dynamically by applying  a transform to each point in the linked path . The path reference does not change its linked path in any way so you can have many path references  each linked to the same path.

A non-area path reference can be un-referenced.  In which case a completely new path is created that no longer references the original vertex list but has its own vertex list.
