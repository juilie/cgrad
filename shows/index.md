---
layout: default
title: Shows | Calvin Grad
css: "/static/css/shows.css"
---
<div class="show-container">
    <section>
      <h2>Upcoming</h2>
      {% assign shows = site.shows | default: array %}
      {% assign current_time = site.time | date: '%s' %}
      {% assign upcoming_shows = '' | split: '' %}
      {% for show in shows %}
        {% assign show_time = show.date | date: '%s' %}
        {% if show_time >= current_time %}
          {% assign upcoming_shows = upcoming_shows | push: show %}
        {% endif %}
      {% endfor %}
      {% assign upcoming_shows = upcoming_shows | sort: 'date' %}
      
      {% if upcoming_shows.size > 0 %}
        {% for show in upcoming_shows %}
          <article class="show-tile">
            <div class="show-info">
              <h3 class="show-town">{{ show.town }}</h3>
              <div class="show-details">
              <div class="show-date-venue">
                <span class="show-date">{{ show.date | date: "%B %d" }}</span>
                <span class="show-venue">{{ show.venue }}</span>
                </div>
                  <span class="show-time">{{ show.date | date: "%-I:%M %p" | strip }}</span>
              </div>
              {% if show.support %}
                <span class="show-support">w/ {{ show.support }}</span>
              {% endif %}
            </div>
            {% if show.ticket_link %}
              <div class="ticket-info">
                <a href="{{ show.ticket_link }}" class="ticket-link">Tickets</a>
              </div>
            {% endif %}
          </article>
        {% endfor %}
      {% else %}
        <section></section>
      {% endif %}
    </section>

    <section class="past-shows">
      <h2>Past</h2>
      {% assign past_shows = '' | split: '' %}
      {% for show in shows %}
        {% assign show_time = show.date | date: '%s' %}
        {% if show_time < current_time %}
          {% assign past_shows = past_shows | push: show %}
        {% endif %}
      {% endfor %}
      {% assign past_shows = past_shows | sort: 'date' | reverse %}
      
      {% if past_shows.size > 0 %}
        {% for show in past_shows %}
          <article class="show-tile">
            <div class="show-info">
              <h3 class="show-town">{{ show.town }}</h3>
              <div class="show-details">
                <span class="show-date">{{ show.date | date: "%B %d" }}</span>
                <span class="show-venue">{{ show.venue }}</span>
              </div>
              {% if show.support %}
                <span class="show-support">w/ {{ show.support }}</span>
              {% endif %}
            </div>
            {% if show.ticket_link %}
              <div class="ticket-info">
                <a href="{{ show.ticket_link }}" class="ticket-link">Tickets</a>
              </div>
            {% endif %}
          </article>
        {% endfor %}
      {% else %}
        <section></section>
      {% endif %}
    </section>
</div>