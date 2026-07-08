---
author: Kris Hollingsworth
title: "Tools for Creating Accessible Math Content"
subtitle: false
date: 2026-07-01
pinned: true
hidden: true
description: "Toolshop for content creators of accessible mathematics."
excerpt: |
  My own maintained list of free and/or open-source tools for creating accessible math content. It remains a work in progress, but you may find it useful for creating your own accessible content, or even just understanding what tools are available to you.
  
  Based on work originally started in a working group with Steven Clontz, Lilly Webster, and myself at the Doenet 2026 Community Workshop.
mathjax: true
tags: ["accessibility", "tools"]
---
## Tools for Creating Accessible Math Content

<strong>Last Updated:</strong> {{ site.data.tool-ecosystem.last_updated | date: "%B %-d, %Y" }}

{% include tools-toc.html %}

### My Workflow

For those interested, my pipeline for creating content for my students is:
Markdown (authored in Obsidian.md) -> pandoc -> html -> LMS (D2L in my case).

My markdown often included embedded manipulatives from the activity creation sections below, primarily Doenet. You can see samples in my Calculus II notes on my teaching page, and other course note samples will be available after the Fall 2026 semester.


{% include generic-data-blocks.html source=site.data.tool-ecosystem.authoring title="Authoring Languages" %}
{% include generic-data-blocks.html source=site.data.tool-ecosystem.format_conversion title="Format Conversion Tools" %}
{% include generic-data-blocks.html source=site.data.tool-ecosystem.activity_creation title="Interactive Activities or Exercises" %}
{% include generic-data-blocks.html source=site.data.tool-ecosystem.hosting_deployment title="Hosting and Deployment Tools" %}
{% include generic-data-blocks.html source=site.data.tool-ecosystem.accessibility_checkers title="Tools to Check Accessibility Standards" %}
{% include generic-data-blocks.html source=site.data.tool-ecosystem.student_data_collection title="Student Data Collection" %}