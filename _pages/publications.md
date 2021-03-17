---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

2019
======
- ["Good, Better, Best: Textual Distractors Generation for Multi-Choice VQA via Policy Gradient"](https://arxiv.org/abs/1910.09134). Jiaying Lu, Xin Ye, Yi Ren and Yezhou Yang. Technical Report 1910.09134, arXiv, 2019.
