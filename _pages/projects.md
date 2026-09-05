---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
og_image: og-projects.png
og_title: "Quantitative investment projects: public data, public code"
description: "Does physical climate risk show up in share prices? A live study on 302 listed companies, with the data layer already public and its code on GitHub."
---

{% include base_path %}

Alongside my other academic research, I also work on quantitative questions in financial markets. These are self-directed research exercises using public data. Each write-up states the question, the data, the method, and the result, including where the result was null, and links to the code so the analysis can be reproduced.

{% assign projects = site.projects | sort: "date" | reverse %}
{% for post in projects %}
{% include archive-single-project.html %}
{% endfor %}

## In progress

One study is running. The write-up goes up here with its code when it is done.

**Climate risk as an equity signal.** Companies own physical things. Power stations, pipelines, mines, cement works. Those things sit in places, and places have weather. The question is whether investors price the risk that weather damages those assets or interrupts what they produce. If they do, companies with more exposed assets should earn different returns from companies with less exposed ones, once everything else known to move share prices has been controlled for.

The hard part is not the question, it is the join. Three ingredients are needed and none of them connects to the others: which company owns which asset, what each company's shares did daily, and the known drivers of returns used as controls. The ownership data names companies by legal identifier, the price data is organised by ticker, and neither contains the other. So most of the work so far has been building that bridge and then trying to prove it wrong. 302 of 328 ownership entities resolve to a tradeable listing, covering 4,900 of 5,115 tracked assets. The price panel holds 1.1 million daily rows and passes 16 of 16 integrity checks.

The test itself is still ahead. The method is a factor decomposition: returns are separated into exposures to known risk factors and a residual, so the question becomes whether hazard exposure carries anything those factors do not already explain. Survivorship bias and transaction costs are handled explicitly rather than assumed away, and the choice of estimation window is stated instead of tuned. The design is written as a pre-analysis plan and fixed before estimation, so the specification cannot drift towards a result. A well-documented null is a finding and will be published as one.

**Revised 21 August 2026.** I computed the minimum detectable effect before running the test and found the cross-sectional design underpowered: it would need roughly a century of data to detect a plausible effect. So the primary design is now an event study, and the cross-sectional test is reported with its minimum detectable effect rather than quietly dropped. The revision is dated and the reasoning is in the repository. Changing a design because it cannot answer the question is the point of writing the plan down first; changing it because the answer was disappointing is what the plan exists to prevent.

The data-acquisition layer is public and deliberately independent of the test: [github.com/ochofer/paper1-hazard-exposure-data](https://github.com/ochofer/paper1-hazard-exposure-data){: target="_blank"}. Two commitments were written into it before there was a hypothesis to test: how survivorship bias is handled, including point-in-time universe construction and the treatment of delisting returns, and how transaction costs are charged, on turnover, reported gross and net, with the break-even cost as the headline. The repository also reports what the survivorship measurement actually found, including where it came back inconclusive at the company sizes that matter here. That independence is why the August revision to the design required no change to the data layer at all.

**Next: company valuation of a less-covered Dutch listed name.** A three-statement valuation from the company's own accounts, with driver-based forecasts from segment disclosure and sensitivity analysis on the assumptions that actually move the answer. The conclusion will be a range rather than a point estimate, together with what would have to be true for the downside case to be the right one. Not started yet; it goes up here with its code when it is done.

Each project publishes its code in a public repository as its write-up goes up, so the analysis can be run rather than taken on trust.

For written analysis aimed at decision-makers rather than academic readers, see the two DEMETRA policy briefs under [Publications](/publications/).
