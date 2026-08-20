---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

Alongside my other academic research, I also work on quantitative questions in financial markets. These are self-directed research exercises using public data. Each write-up states the question, the data, the method, and the result, including where the result was null, and links to the code so the analysis can be reproduced.

{% assign projects = site.projects | sort: "date" | reverse %}
{% for post in projects %}
{% include archive-single-project.html %}
{% endfor %}

## In progress

The first write-ups go live in September 2026. Three projects are running at the moment.

**Factor decomposition and performance attribution.** Separates an equity portfolio's return against its benchmark into factor exposures and a residual, so the question becomes where performance came from rather than whether the picks won. Survivorship bias and transaction costs are handled explicitly rather than assumed away, and the choice of estimation window is stated instead of tuned.

**Climate hazard exposure as an equity signal.** A firm-level physical-risk measure built from asset-level ownership data, covering the 328 listed firms with reliable coverage, tested against the cross-section of returns after factor controls. The design is written as a pre-analysis plan and fixed before estimation, so the specification cannot drift towards a result. A well-documented null is a finding and will be published as one.

The data-acquisition layer is already public, ahead of any analysis: [github.com/ochofer/paper1-hazard-exposure-data](https://github.com/ochofer/paper1-hazard-exposure-data){: target="_blank"}. Its README fixes two things in writing before a single result exists, which is the point at which such decisions are still honest ones: how survivorship bias will be handled, including point-in-time universe construction and the treatment of delisting returns, and how transaction costs will be charged, on turnover, reported gross and net, with the break-even cost as the headline. It also records which questions are still open.

**Company valuation of a less-covered Dutch listed name.** A three-statement valuation built from the company's own accounts, with driver-based forecasts from segment disclosure and sensitivity analysis on the assumptions that actually move the answer. The conclusion is a range rather than a point estimate, together with what would have to be true for the downside case to be the right one.

Each project publishes its code in a public repository as its write-up goes up, so the analysis can be run rather than taken on trust.

For written analysis aimed at decision-makers rather than academic readers, see the two DEMETRA policy briefs under [Publications](/publications/).
