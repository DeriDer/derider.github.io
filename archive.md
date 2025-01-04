---
layout: default
title: Archive
permalink: /archive/
pagination: true
---

## Archive

Welcome to the archive! Here you'll find a list of all my posts organized by year.

## Posts by Year

<ul>
  {% assign current_year = "" %}
  {% for post in site.posts %}
    {% capture year %}{{ post.date | date: "%Y" }}{% endcapture %}
    {% unless year == current_year %}
      {% assign current_year = year %}
      <h2>{{ current_year }}</h2>
    {% endunless %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span>({{ post.date | date: "%B %d, %Y" }})</span>
    </li>
  {% endfor %}
</ul>

<!-- Pagination Links -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}">&larr; Previous</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}">Next &rarr;</a>
  {% endif %}
</div>
