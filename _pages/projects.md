---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

Alongside my academic research, I work on quantitative questions in financial markets. These are self-directed research exercises using public data, not a performance record. Each write-up states the question, the data, the method, and the result, including where the result was null, and links to the code so the analysis can be reproduced.

{% assign projects = site.projects | sort: "date" | reverse %}
{% for post in projects %}
{% include archive-single-project.html %}
{% endfor %}

## In progress

The first write-ups go live in September 2026. Three questions are open at the moment.

**Where does a portfolio's performance actually come from?** A factor decomposition of a small equity portfolio against its benchmark, separating the part of the return that known risk factors already explain from whatever is left over. The output is an attribution rather than a performance figure, and survivorship bias, transaction costs and the choice of estimation window are handled explicitly rather than left to the reader to worry about.

**Does an outside signal carry information that the market price does not already contain?** Prices aggregate a great deal on their own, so the useful test of any real-world signal is whether it adds anything once the price is accounted for. That is a harder question than whether the signal correlates with returns, and it needs a holdout, a correction for multiple testing, and a mechanism stated in advance rather than found afterwards. A well-documented null answer is a result and will be published as one.

**What is a less-covered Dutch listed company worth?** A full valuation of a name outside the heavily covered end of the market, with the assumptions set out as a table and the sensitivities as a grid. The conclusion is a range rather than a point estimate, together with what would have to be true for the downside case to be the right one.

Each project publishes its code in a public repository, so the analysis can be run rather than taken on trust.

For written analysis aimed at decision-makers rather than academic readers, see the two DEMETRA policy briefs under [Publications](/publications/).
