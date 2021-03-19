---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<!-- Mantained by BibBase -->
<script src="https://bibbase.org/show?bib=https%3A%2F%2Flujiaying.github.io%2Ffiles%2Fmypubs.bib&commas=true&jsonp=1"></script>
