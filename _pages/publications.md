---
layout: archive
title: "Featured Publications"
permalink: /publications/
author_profile: true
---

<!-- {% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %} -->
<!-- This page shows selected publications. For a complete list, please visit my [Google Scholar](https://scholar.google.com/citations?user=1HY3TXcAAAAJ&hl=en&authuser=2) page. -->

{% include base_path %}

{% assign show_preprints = true %}
{% if show_preprints %}
Preprints
------
{% endif %}
{% for post in site.publications reversed %}
  {% if post.status == "preprint" %}
    {% if post.include_on_website %}
      {% include publication-single.html %}
    {% endif %}
  {% endif %}
{% endfor %}

Journal Articles
------
{% for post in site.publications reversed %}
  {% if post.status == "journal"%}
    {% unless post.type contains "thesis" %}
      {% if post.include_on_website %}
        {% include publication-single.html %}
      {% endif %}
    {% endunless %}
  {% endif %}
{% endfor %}

Refereed Conference Papers
------
{% for post in site.publications reversed %}
  {% if post.status == "conference"%}
    {% unless post.type contains "thesis" %}
      {% if post.include_on_website %}
        {% include publication-single.html %}
      {% endif %}
    {% endunless %}
  {% endif %}
{% endfor %}