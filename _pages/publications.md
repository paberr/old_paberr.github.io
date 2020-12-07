---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign postsByYear =
    site.publications | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear reversed %}
  <h2 id="y{{ year.name }}">{{ year.name }}</h2>
  {% for post in year.items %}
    {% include publication-single.html %}
  {% endfor %}
{% endfor %}
