---
layout: page
title: "Publications"
permalink: /publications/
page_style: publications
eyebrow: "Publications / Selected and complete"
headline: "Statistical methods for data with curves, regimes, and changing structure."
deck: >-
  Publication records are also available through [Google
  Scholar](https://scholar.google.com/citations?user=CYLjVg4AAAAJ&hl=en) and
  [Academia](https://um-boston.academia.edu/DavidDegras).
---

<section class="selected-publications" aria-labelledby="selected-publications-heading">
  <div class="archive-section-heading">
    <p class="research-kicker">Selected work</p>
    <h2 id="selected-publications-heading">Recent methods and applications</h2>
  </div>
  <div class="selected-publication-list">
    <a class="selected-publication" href="{{ '/publications/scalable-feature-matching-large-data-collections/' | relative_url }}"><span class="selected-publication-year">2023</span><span><strong>Scalable Feature Matching Across Large Data Collections</strong><small>Journal of Computational and Graphical Statistics · neuroimaging databases</small></span><span aria-hidden="true">↗</span></a>
    <a class="selected-publication" href="{{ '/publications/markov-switching-state-space-models-neuroimaging/' | relative_url }}"><span class="selected-publication-year">2022</span><span><strong>Markov-switching state-space models with applications to neuroimaging</strong><small>Computational Statistics &amp; Data Analysis · EEG and latent regimes</small></span><span aria-hidden="true">↗</span></a>
    <a class="selected-publication" href="{{ '/publications/sparse-group-fused-lasso-model-segmentation/' | relative_url }}"><span class="selected-publication-year">2020</span><span><strong>Sparse group fused lasso for model segmentation</strong><small>Advances in Data Analysis and Classification · sparse high-dimensional models</small></span><span aria-hidden="true">↗</span></a>
  </div>
</section>

<section class="complete-publications" aria-labelledby="complete-publications-heading">
  <div class="archive-section-heading">
    <p class="research-kicker">Complete record</p>
    <h2 id="complete-publications-heading">Papers and monograph</h2>
  </div>
  {% assign publications = site.publications | sort: "date" | reverse %}
  {% assign last_year = "" %}
  {% for post in publications %}
    {% capture publication_year %}{{ post.date | date: "%Y" }}{% endcapture %}
    {% if publication_year != last_year %}
      <h3 class="publication-year">{{ publication_year }}</h3>
      {% assign last_year = publication_year %}
    {% endif %}
    {% include publication-item.html publication=post %}
  {% endfor %}
</section>
