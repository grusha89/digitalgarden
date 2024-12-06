---
layout: page
title: Home
id: home
permalink: /
---
 
# wflow Wiki ![alt text](image-1.png)

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
  Take a look at <span style="font-weight: bold">[[Table of content]]</span> to get started on your exploration.
</p>

This digital garden of wflow documentation is constantly updated. Feel free to let us know what else should be added. If you find some mistakes or contradictions you're more than welcome to contact us (QA team)


<strong>Recently updated notes</strong>

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 5 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
