---
layout: page
permalink: /teaching/
title: teaching
description: Learning material for the courses I teach will be updated here.
nav: true
social: true
---

Will be updated soon!

<div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <h2 class="category">{{category}}</h2>
      {% assign categorized_projects = site.projects | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <!-- Generate cards for each project -->
      {% if page.horizontal %}
        <!-- <div class="container">
          <div class="row row-cols-2">
          {% for project in sorted_projects %}
            {% include projects_horizontal.html %}
          {% endfor %}
          </div>
        </div> -->
      {% else %}
        <!-- <div class="grid">
          {% for project in sorted_projects %}
            {% include projects.html %}
          {% endfor %}
        </div> -->
      {% endif %}
    {% endfor %}

  {% else %}
  <!-- Display projects without categories -->
    {% assign sorted_projects = site.projects | sort: "importance" %}
    <!-- Generate cards for each project -->
    {% if page.horizontal %}
      <!-- <div class="container">
        <div class="row row-cols-2">
        {% for project in sorted_projects %}
          {% include projects_hrz.html %}
        {% endfor %}
        </div>
      </div> -->
      <!-- <div class="grid">
        {% for project in sorted_projects %}
        {% endfor %}
      </div> -->
    {% endif %}

  {% endif %}
  {% if page.social %}
    <div class="social">
      <div class="contact-icons">
        {% include social.html %}
      </div>
      <div class="contact-note">{{ site.contact_note }}</div>
    </div>
    {% endif %}

</div>
