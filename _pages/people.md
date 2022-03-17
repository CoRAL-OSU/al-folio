---
layout: page
title: People
permalink: /people/
description: Present and past members of CoRAL
nav: true
display_categories: [graduate, undergraduate, past]
horizontal: false
---

<!-- pages/projects.md -->
<div class="people-page">
{%- if site.enable_project_categories and page.display_categories %}

  {%- assign person = site.people | where: "category", "director" | first -%}
  <div class="container card person-post">
              <div class="row">
                    <div class="col-sm-3 my-auto">
                        <img src="{{site.baseurl}}/assets/img/people/{{person.image}}" class="img-fluid person-headshot shadow-lg ">
                    </div>
                    <div class="col-sm-9 my-auto">
                        <h4 class="person-name">{{person.name}}</h4>
                        <h4 class="person-role">{{person.role}}</h4>
                        {{person.content}}
                    </div>
              </div>
    </div>

  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_people = site.people | where: "category", category -%}

  <!-- Generate cards for each project -->
  {%- for person in categorized_people -%}
    <div class="container card person-post">
              <div class="row">
                  {%- if person.category != "past" -%}
                    <div class="col-sm-2 my-auto">
                        <img src="{{site.baseurl}}/assets/img/people/{{person.image}}" class="img-fluid person-headshot shadow-lg ">
                    </div>
                    <div class="col-sm-10 my-auto">
                        <h4 class="person-name">{{person.name}}</h4>
                        <p class="person-info"><strong>Interests: </strong>{{person.interests}}</p>
                        <p class="person-info">{{person.contact}}</p>
                    </div>
                  {%- else -%}
                    <div class="col-sm-12 my-auto">
                      <h4 class="person-name">{{person.name}}</h4>
                      <h5 class="person-position">{{person.year}}</h5>
                      <p class="person-info"></strong>{{person.info}}</p>
                    </div>
                  {%- endif -%}
              </div>
    </div>
  {%- endfor %}
  {% endfor %}

{%- endif -%}

</div>
