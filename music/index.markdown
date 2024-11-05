---
layout: default
title: Music
css: "/static/css/music.css"
---

<div class="music-container">
  {% assign all_projects = site.music_projects | where: "active", true %}
  
  {% assign solo_work = all_projects | where: "category", "Solo Work" %}
  {% assign bands = all_projects | where: "category", "Bands & Projects" %}
  {% assign ensembles = all_projects | where: "category", "Ensembles" %}

  {% if solo_work.size > 0 %}
  <section class="project">
    <h2>Solo Work</h2>
    {% for project in solo_work %}
      <div class="project-tile">
        <div class="project-info">
          <h3>{{ project.title }}</h3>
          {% if project.description %}
            <p>{{ project.description }}</p>
          {% endif %}
          {% if project.links %}
            <div class="project-links">
              {% for link in project.links %}
                <a href="{{ link.url }}" class="music-link">{{ link.text }}</a>
              {% endfor %}
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </section>
  {% endif %}

  {% if bands.size > 0 %}
  <section class="project">
    <h2>Bands & Projects</h2>
    {% for project in bands %}
      <div class="project-tile">
        <div class="project-info">
          <h3>{{ project.title }}</h3>
          {% if project.description %}
            <p>{{ project.description }}</p>
          {% endif %}
          {% if project.links %}
            <div class="project-links">
              {% for link in project.links %}
                <a href="{{ link.url }}" class="music-link">{{ link.text }}</a>
              {% endfor %}
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </section>
  {% endif %}

  {% if ensembles.size > 0 %}
  <section class="project">
    <h2>Ensembles</h2>
    {% for project in ensembles %}
      <div class="project-tile">
        <div class="project-info">
          <h3>{{ project.title }}</h3>
          {% if project.description %}
            <p>{{ project.description }}</p>
          {% endif %}
          {% if project.links %}
            <div class="project-links">
              {% for link in project.links %}
                <a href="{{ link.url }}" class="music-link">{{ link.text }}</a>
              {% endfor %}
            </div>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </section>
  {% endif %}
</div>