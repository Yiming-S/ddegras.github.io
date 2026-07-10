---
layout: page
title: "People"
permalink: /people/
page_style: people
---

<p class="people-intro">I supervise and collaborate on statistical learning, functional data analysis, scientific computing, neuroimaging, and related data-intensive problems. For research inquiries, contact <a href="mailto:David.Degras@umb.edu">David Degras-Valabregue</a> or connect through <a href="https://github.com/ddegras">GitHub</a>.</p>

<div class="people-directory">
  {% for person in site.data.people.people %}
    <article class="person-record">
      <p class="person-category">{{ person.category }}</p>
      <div class="person-record__body">
        <h2><a href="{{ person.url }}">{{ person.name }}</a></h2>
        <p class="person-status">{{ person.status }}</p>
        {% if person.description %}
          <div class="person-description">{{ person.description | markdownify }}</div>
        {% endif %}
      </div>
    </article>
  {% endfor %}
</div>
