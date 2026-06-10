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
  <div style="margin:0 0 2px 0; font-size:15px;">
    <span class="title"></span>
  </div>
  <div style="font-size:13px; color:#555; margin-bottom:2px;">
    <span class="author"></span>
  </div>
  <div style="font-size:13px; margin-bottom:4px;">
    <span class="if booktitle"><em style="color:#185FA5"><span class="booktitle"></span></em></span>
    <span class="if journal"><em style="color:#185FA5"><span class="journal"></span></em></span>
    <span class="if year">, <span class="year"></span></span>
  </div>
  <div style="font-size:12px; margin-bottom:10px;">
    <span class="if url_Paper"><a class="bibtexVar" href="+url_Paper+" extra="url_Paper" target="_blank" style="color:#993C1D">Paper</a> &nbsp;</span>
    <span class="if url_arXiv"><a class="bibtexVar" href="+url_arXiv+" extra="url_arXiv" target="_blank" style="color:#534AB7">arXiv</a> &nbsp;</span>
    <span class="if url_Code"><a class="bibtexVar" href="+url_Code+" extra="url_Code" target="_blank" style="color:#0F6E56">Code</a> &nbsp;</span>
    <span class="if doi"><a class="bibtexVar" href="https://doi.org/+doi+" extra="doi" target="_blank" style="color:#5F5E5A">DOI</a></span>
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
