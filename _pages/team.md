---
layout: page
title: team
permalink: /team/
description: A group of people who devoted to next-generation autonomous driving technology.
nav: true
nav_order: 1
display_categories: [Faculty or Visiting Scholar or Joint Ph.D, Intern or Visiting Student]
display_categories: [Faculty or Visiting Scholar or Joint Ph.D, Intern or Visiting Student, Alumni]
---

<div class="team">
    {% for category in page.display_categories %}
    <h2 class="category">{{ category }}</h2>

    <div class="grid">
    {% assign categorized_people = site.team | where: "category", category%}
    {% assign people_sorted = categorized_people | sort: "order" %}
    {% for people_item in people_sorted %}
        {% include people.html %}
    {% endfor %}
    </div>
    {% endfor %}
</div>