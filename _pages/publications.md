---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

{% if page.author and site.data.authors[page.author] %}
  {% assign author = site.data.authors[page.author] %}{% else %}{% assign author = site.author %}
{% endif %}
{% if author.googlescholar %}
You can also find my publications on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

<p>* indcates co-first author, # indicates co-corresponding author.</p> 

<!-- bibtex-js -->
<script src="https://cdn.jsdelivr.net/npm/bibtex-js@1.0.5/dist/bibtex-js.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bibtex-js@1.0.5/dist/bibtex-js.css">

  <div class="bibtex_template">
    <div class="if author" style="font-weight: bold;">
      <span class="if author"><span class="author"></span>, </span>
      <span class="if year">(<span class="year"></span>). </span>
      "<span class="title"></span>".
      <span class="if journal"><em><span class="journal"></span></em>, </span>
      <span class="if volume">vol. <span class="volume"></span>, </span>
      <span class="if pages">pp. <span class="pages"></span>, </span>
      <span class="if publisher"><span class="publisher"></span>.</span>
    </div>
    <div style="display:none"><span class="bibtexkey"></span></div>
  </div>
  <div class="bibtex_display" bibtexfiles="files/mypubs.bib"></div>

<!-- Mantained by BibBase -->
<!--<script src="https://bibbase.org/show?bib=https%3A%2F%2Fraw.githubusercontent.com%2Flujiaying%2Flujiaying.github.io%2Fmaster%2Ffiles%2Fmypubs.bib&commas=false&fullnames=1&jsonp=1"></script> -->
