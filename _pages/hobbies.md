---
layout: page
title: hobbies
permalink: /hobbies/
description: My Hobbies - Dhyey Shah.
nav: true
nav_order: 5
display_categories: []
horizontal: false
---

<!-- pages/projects.md -->
Beyond my academic and research activities, I really enjoy engaging in a range of activities that keep me both physically active and creatively inspired. I am an avid sports enthusiast and regularly play and follow cricket, tennis, badminton, cycling, and have recently developed a strong interest in rock climbing. I also like spending time outdoors, especially going on hikes with friends. On the creative side, I like painting and writing often journaling or expressing my thoughts through poetry. Additionally, I have a deep curiosity for subjects such as psychology, philosophy, and neuroscience, which I explore through reading in my free time.

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
