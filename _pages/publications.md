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

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<!-- Mantained by BibBase -->
<script src="https://bibbase.org/show?bib=https%3A%2F%2Fraw.githubusercontent.com%2Flujiaying%2Flujiaying.github.io%2Fmaster%2Ffiles%2Fmypubs.bib&commas=false&fullnames=1&jsonp=1"></script>

## Selected Posters
- Shuyue Jiang, Wenjing Ma, Runze Yan, Chang Su, and **Jiaying Lu**. Chronological age prediction based on dna methylation and clinical features. AMIA 2025 Annual Symposium, (2025).
- Shifan Zhao, Chen Yue, Jiexin Zheng, and **Jiaying Lu**. Privacy-preserving synthetic data generation with large language models for enhanced discourse-based adrd assessmen. AMIA 2025 Annual Symposum, (2025).
