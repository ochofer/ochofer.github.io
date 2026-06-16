---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% assign articles = site.publications | where: "category", "articles" | sort: "date" | reverse %}
{% if articles.size > 0 %}
## Journal articles
{% for post in articles %}
{% include archive-single.html %}
{% endfor %}
{% endif %}

{% assign wps = site.publications | where: "category", "working-papers" | sort: "date" | reverse %}
{% if wps.size > 0 %}
## Working papers
{% for post in wps %}
{% include archive-single.html %}
{% endfor %}
{% endif %}

{% assign data = site.publications | where: "category", "datasets" | sort: "date" | reverse %}
{% if data.size > 0 %}
## Datasets
{% for post in data %}
{% include archive-single.html %}
{% endfor %}
{% endif %}

{% assign briefs = site.publications | where: "category", "policy-briefs" | sort: "date" | reverse %}
{% if briefs.size > 0 %}
## Policy briefs
{% for post in briefs %}
{% include archive-single.html %}
{% endfor %}
{% endif %}
