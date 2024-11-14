---
layout: page
title: Projects
permalink: /projects/
description: A brief look into some projects I've made over the years
nav: true
nav_order: 1
# display_categories: [fun]
horizontal: false
---

<style>
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.grid .card {
  height: 400px;  /* fixed total height for card */
  display: flex;
  flex-direction: column;
}

.grid .card img {
  width: 100%;
  height: 200px;  /* fixed height for images */
  object-fit: cover;
  flex-shrink: 0;  /* prevent image from shrinking */
}

.grid .card .card-body {
  flex: 1;
  padding: 15px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.grid .card .card-title {
  font-size: 1.2rem;
  margin-bottom: 8px;
  display: -webkit-box;
  -webkit-line-clamp: 2;  /* limit title to 2 lines */
  -webkit-box-orient: vertical;
  overflow: hidden;
  flex-shrink: 0;  /* prevent title from shrinking */
}

.grid .card .card-text {
  display: -webkit-box;
  -webkit-line-clamp: 4;  /* limit description to 4 lines */
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  font-size: 0.9rem;
}
</style>

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
