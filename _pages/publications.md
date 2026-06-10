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
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/pcooksey/bibtex-js@1.0.0/src/bibtex_js.js"></script>
<bibtex src="../files/mypubs.bib"></bibtex>

<div id="bibtex_display"></div>

<div class="bibtex_template">
  <div class="if author" style="font-weight: bold;">
    <span class="if year">
      <span class="year"></span>,
    </span>
    <span class="author"></span>
    <span class="if url" style="margin-left: 20px">
      <a class="url" style="color:black; font-size:10px">(view online)</a>
    </span>
  </div>
  <div style="margin-left: 10px; margin-bottom:5px;">
    <span class="title"></span>
  </div>
</div>

<div class="bibtex_structure">
  <div class="sections bibtextypekey">
    <div class="section article">
      <h1>Journal Articles</h1>
      <div class="sort year" extra="DESC number">
        <div class="templates"></div>
      </div>
    </div>
    <div class="section book">
      <h1>Books</h1>
      <div class="sort year" extra="DESC number">
        <div class="templates"></div>
      </div>
    </div>
    <div class="section inproceedings">
      <h1>Conference and Workshop Papers</h1>
      <div class="sort year" extra="DESC number">
        <div class="templates"></div>
      </div>
    </div>
    <div class="section misc|phdthesis|mastersthesis|bachelorsthesis|techreport">
      <h1>Preprints</h1>
      <div class="sort year" extra="DESC number">
        <div class="templates"></div>
      </div>
    </div>
  </div>
</div>
