---
layout: page
title: People
permalink: /people/
description: Present and past members of CoRAL
nav: true
display_categories: [Graduate, Undergraduate]
horizontal: false
---

<!-- pages/people.md -->
<div class="people-page">
{%- if page.display_categories %}

  <!-- Dr. Bai's section -->
  {%- assign person = site.people | where: "category", "director" | first -%}
  <div class="container card person-post">
              <div class="row">
                    <div class="col-sm-3 my-auto">
                        <img src="{{site.baseurl}}/assets/img/people/{{person.image}}" class="img-fluid person-headshot shadow-lg ">
                    </div>
                    <div class="col-sm-9 my-auto">
                        <h4 class="person-name">Director: {{person.name}}</h4>
                        <h4 class="person-role">{{person.role}}</h4>
                        {{person.content}}
                    </div>
              </div>
    </div>

  <!-- Display categories -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_people = site.people | where: "category", category -%}

  <!-- Generate card for each person -->
  {%- for person in categorized_people -%}
    {%- if person.current -%}
    <div class="container card person-post">
              <div class="row">
                    {%- if person.image -%}
                    <div class="col-sm-2 my-auto">
                        <img src="{{site.baseurl}}/assets/img/people/{{person.image}}" class="img-fluid person-headshot shadow-lg ">
                    </div>
                    {% else %}
                    <div class="col-sm-2 my-auto">
                    </div>
                    {% endif %}
                    <div class="col-sm-10 my-auto">
                        <h4 class="person-name">{{person.name}}</h4>
                        <p class="person-info"><strong>Interests: </strong>{{person.interests}}</p>
                        <p class="person-info">{{person.contact}}</p>
                    </div>
              </div>
    </div>
    {% endif %}
  {% endfor %}
  {% endfor %}

  <h2 class="category">Past Members</h2>
  <div class="container card person-post">
  <!-- Handle past members sorted by year in decreasing order -->
  {% assign members_by_year = site.people | sort: 'year' | reverse %}
  {% for member in members_by_year %}
    <!-- Only include members not currently working with coral -->
    {% if member.current != true %}
      <div class="container">
        <div class="my-auto">
          <p><strong>{{member.name}}</strong>{% if member.position %}, {{member.position}}, {% endif %} ({{member.purpose}} {{member.year}})</p>
          <p class="person-info"><i>{{member.work}}</i></p>
          <hr>
        </div>
      </div>
    {% endif %}
  {% endfor %}
  </div>
{%- endif -%}

</div>
