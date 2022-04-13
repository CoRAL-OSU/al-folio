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
  
  {% assign years = site.projects | group_by: "year" %}
  {% assign yearsSorted = years | sort: "name" | reverse %}


  <!-- Iterate through projects -->
  
  {% for y in yearsSorted %}
    <!-- For every project, include the code found in projects.html -->
    <!-- This file defines the display card format and links to the project's own page -->
    <h2 class="category">{{y.name}}</h2>
    <div>
      {% assign yearImportanceSorted = y.items | sort: "importance" | reverse %}
      {% for project in yearImportanceSorted %}
        {% include projects.html %}
      {% endfor %}
    </div>
  {% endfor %}
</div>