---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% assign cats = "articles,working-papers,datasets,policy-briefs" | split: "," %}
{% assign labels = "Journal articles,Working papers,Datasets,Policy briefs" | split: "," %}

{% for cat in cats %}
  {% assign label = labels[forloop.index0] %}
  {% assign pubs = site.publications | where: "category", cat | sort: "date" | reverse %}
  {% if pubs.size > 0 %}
## {{ label }}

    {% for post in pubs %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}
