---
layout: page
title: "Presentations"
permalink: /presentations/
page_style: presentations
eyebrow: "Presentations / Seminars and conferences"
headline: "Ideas in conversation with mathematical and scientific communities."
deck: >-
  Selected invited talks, conference presentations, seminars, and tutorials
  are collected here as verified records become available.
redirect_from:
  - /talks/
---

{% assign presentations = site.data.presentations.presentations | sort: "date" | reverse %}
{% if presentations and presentations.size > 0 %}
  <div class="presentation-list">
    {% assign last_year = "" %}
    {% for presentation in presentations %}
      {% capture presentation_year %}{{ presentation.date | date: "%Y" }}{% endcapture %}
      {% if presentation_year != last_year %}
        <h2 class="presentation-year">{{ presentation_year }}</h2>
        {% assign last_year = presentation_year %}
      {% endif %}
      <article class="presentation-record">
        <time datetime="{{ presentation.date }}">{{ presentation.date | date: "%b %-d, %Y" }}</time>
        <div class="presentation-record__body">
          <p class="presentation-type">{{ presentation.type | default: "Presentation" }}</p>
          <h3>{{ presentation.title }}</h3>
          <p class="presentation-meta">{{ presentation.event }}{% if presentation.location %} · {{ presentation.location }}{% endif %}</p>
          {% if presentation.description %}<p class="presentation-description">{{ presentation.description }}</p>{% endif %}
          {% if presentation.slides or presentation.video or presentation.event_url %}
            <p class="presentation-links">
              {% if presentation.slides %}
                {% capture slides_href %}{% if presentation.slides contains '://' %}{{ presentation.slides }}{% else %}{{ presentation.slides | relative_url }}{% endif %}{% endcapture %}
                <a href="{{ slides_href | strip }}">Slides <span aria-hidden="true">↗</span></a>
              {% endif %}
              {% if presentation.video %}<a href="{{ presentation.video }}">Video <span aria-hidden="true">↗</span></a>{% endif %}
              {% if presentation.event_url %}<a href="{{ presentation.event_url }}">Event <span aria-hidden="true">↗</span></a>{% endif %}
            </p>
          {% endif %}
        </div>
      </article>
    {% endfor %}
  </div>
{% else %}
  <div class="presentation-empty">
    <p>No presentation record is published yet. This section is ready for verified seminar, conference, invited-talk, and tutorial entries.</p>
    <p>For the current research record, see <a href="{{ '/publications/' | relative_url }}">Publications</a> or <a href="https://scholar.google.com/citations?user=CYLjVg4AAAAJ&amp;hl=en">Google Scholar</a>.</p>
  </div>
{% endif %}
