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

<textarea id="bibtex_input" style="display:none;">
@book{book1,
  author = "Donald Knuth",
  title = "Concrete Mathematics"
}
</textarea>

<div id="bibtex_display"></div>

<!-- Mantained by BibBase -->
<!--<script src="https://bibbase.org/show?bib=https%3A%2F%2Fraw.githubusercontent.com%2Flujiaying%2Flujiaying.github.io%2Fmaster%2Ffiles%2Fmypubs.bib&commas=false&fullnames=1&jsonp=1"></script> -->
