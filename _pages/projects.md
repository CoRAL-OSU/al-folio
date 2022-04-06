---
layout: page
title: Research
permalink: /projects/
description: CoRAL Research Projects
nav: true
display_categories: []
horizontal: false
---

<!-- pages/projects.md -->

<div class="research-projects">
  <!-- Sort research projects by year -->
  {% assign sorted_projects = site.projects | sort: "year" | reverse %}

  <!-- Iterate through projects -->
  {% for project in sorted_projects %}
    <!-- For every project, include the code found in projects.html -->
    <!-- This file defines the display card format and links to the project's own page -->
    <div>
      {% include projects.html %}
    </div>
  {% endfor %}
</div>