---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

{% include base_path %}

<div class="publication-page-intro">
  <p class="research-kicker">Publications / Selected and complete</p>
  <h2>Statistical methods for data with curves, regimes, and changing structure.</h2>
  <p>Publication records are also available through <a href="https://scholar.google.com/citations?user=CYLjVg4AAAAJ&amp;hl=en">Google Scholar</a> and <a href="https://um-boston.academia.edu/DavidDegras">Academia</a>.</p>
</div>

<section class="selected-publications" aria-labelledby="selected-publications-heading">
  <div class="archive-section-heading">
    <p class="research-kicker">Selected work</p>
    <h2 id="selected-publications-heading">Recent methods and applications</h2>
  </div>
  <div class="selected-publication-list">
    <a class="selected-publication" href="{{ base_path }}/publications/scalable-feature-matching-large-data-collections"><span class="selected-publication-year">2023</span><span><strong>Scalable Feature Matching Across Large Data Collections</strong><small>Journal of Computational and Graphical Statistics · neuroimaging databases</small></span><span aria-hidden="true">↗</span></a>
    <a class="selected-publication" href="{{ base_path }}/publications/markov-switching-state-space-models-neuroimaging"><span class="selected-publication-year">2022</span><span><strong>Markov-switching state-space models with applications to neuroimaging</strong><small>Computational Statistics &amp; Data Analysis · EEG and latent regimes</small></span><span aria-hidden="true">↗</span></a>
    <a class="selected-publication" href="{{ base_path }}/publications/Sparse group fused lasso for model segmentation"><span class="selected-publication-year">2020</span><span><strong>Sparse group fused lasso for model segmentation</strong><small>Advances in Data Analysis and Classification · sparse high-dimensional models</small></span><span aria-hidden="true">↗</span></a>
  </div>
</section>

<section class="complete-publications" aria-labelledby="complete-publications-heading">
  <div class="archive-section-heading">
    <p class="research-kicker">Complete record</p>
    <h2 id="complete-publications-heading">Papers and monograph</h2>
  </div>
  {% assign last_year = "" %}
  {% for post in site.publications reversed %}
    {% if post.year %}
      {% capture publication_year %}{{ post.year }}{% endcapture %}
    {% else %}
      {% capture publication_year %}{{ post.date | date: "%Y" }}{% endcapture %}
    {% endif %}
    {% if publication_year != last_year %}
      <h3 class="publication-year">{{ publication_year }}</h3>
      {% assign last_year = publication_year %}
    {% endif %}
    {% include archive-single.html %}
  {% endfor %}
</section>
