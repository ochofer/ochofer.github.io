---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
og_image: og-projects.png
og_title: "Quantitative investment projects: public data, public code"
description: "Self-directed quantitative research on public market data: factor decomposition, climate hazard exposure as an equity signal, and company valuation."
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

**Climate hazard exposure as an equity signal.** A firm-level physical-risk measure built from asset-level ownership data, on the 302 companies with usable prices out of 328 ownership entities, tested with an event-study design around hazard events, with the cross-sectional test reported alongside it and with its minimum detectable effect. The design is written as a pre-analysis plan and fixed before estimation, so the specification cannot drift towards a result. A well-documented null is a finding and will be published as one.

**Revised 21 August 2026.** I computed the minimum detectable effect before running the test and found the cross-sectional design underpowered: it would need roughly a century of data to detect a plausible effect. So the primary design is now an event study, and the cross-sectional test is reported with its minimum detectable effect rather than quietly dropped. The revision is dated and the reasoning is in the repository. Changing a design because it cannot answer the question is the point of writing the plan down first; changing it because the answer was disappointing is what the plan exists to prevent.

The data-acquisition layer is public and deliberately independent of the test: [github.com/ochofer/paper1-hazard-exposure-data](https://github.com/ochofer/paper1-hazard-exposure-data){: target="_blank"}. Two commitments were written into it before there was a hypothesis to test: how survivorship bias is handled, including point-in-time universe construction and the treatment of delisting returns, and how transaction costs are charged, on turnover, reported gross and net, with the break-even cost as the headline. The repository also reports what the survivorship measurement actually found, including where it came back inconclusive at the company sizes that matter here. That independence is why the August revision to the design required no change to the data layer at all.

**Company valuation of a less-covered Dutch listed name.** A three-statement valuation built from the company's own accounts, with driver-based forecasts from segment disclosure and sensitivity analysis on the assumptions that actually move the answer. The conclusion is a range rather than a point estimate, together with what would have to be true for the downside case to be the right one.

Each project publishes its code in a public repository as its write-up goes up, so the analysis can be run rather than taken on trust.

For written analysis aimed at decision-makers rather than academic readers, see the two DEMETRA policy briefs under [Publications](/publications/).
