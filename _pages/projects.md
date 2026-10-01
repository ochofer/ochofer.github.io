---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
og_image: og-projects.png
og_title: "Quantitative investment projects: public data, public code"
description: "An ownership graph of 328 listed companies holding 5,115 tracked assets, public with its code. I checked 19 apparent ownership changes across two database releases by hand. Twelve had no corporate event behind them."
---

{% include base_path %}

Alongside my other academic research, I also work on quantitative questions in financial markets. These are self-directed research exercises using public data. Each write-up states the question, the data, the method, and the result, including where the result was null, and links to the code so the analysis can be reproduced.

## Ownership and prices

**Climate risk as an equity signal.** Companies own physical things. Power stations, pipelines, mines, cement works. Those things sit in places, and places have weather. The question was whether investors price the risk that weather damages those assets or interrupts what they produce.

The hard part was never the question, it was the join. Which company owns which asset, and what that company's shares did, are recorded in different places under different identifiers, and neither contains the other. So most of the work went into building that bridge and then trying to prove it wrong. The ownership graph is built from Global Energy Monitor's free tracker. 328 ownership entities resolve to the US and developed-Europe listed universe, 302 of them priceable, and all 328 together hold 5,115 tracked assets.

**One return test was specified and set aside before it ran**, on a power calculation published in the repository. A second, pre-registered, was run; its result and the minimum detectable effect that makes it readable are reported in the data-quality note below.

**Most of what a vintage difference records is the file being edited.** I drew 19 apparent ownership changes at random from the 2,543 that two releases of the same database disagree on, and looked for the transaction behind each one in exchange filings, company statements and press releases. Twelve had none. The six that were real arrived 12 and 71 days late for the two recent and heavily covered deals, and 670 to 1,674 days late for the four that were older or smaller, so the recording error is selective, and a constant offset cannot repair it. Two undocumented choices, one the vendor's and one mine, each move a verdict I had committed to in writing before any script ran. What that costs a book: on the 191 firms with any coal or gas exposure, the rank correlation between the two releases is 0.73 under one blank-share convention and 0.77 under the other. The note, its code and its provenance records are public.

[Read the note](https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.1/what-a-vintage-difference-measures.pdf){: target="_blank"} (PDF), or find it under [Publications](/publications/).

The data-acquisition layer is public and deliberately independent of any test: [github.com/ochofer/paper1-hazard-exposure-data](https://github.com/ochofer/paper1-hazard-exposure-data){: target="_blank"}. It was built to be reusable by whatever the analysis turned out to be, which is why setting that test aside required no change to it at all.

## Portfolio construction

**Optimal versus naive diversification.** Every allocator meets the same question sooner or later: is it worth optimising a portfolio, or does naive 1/N, which splits the money equally across assets, do as well? DeMiguel, Garlappi and Uppal (2009) tested a range of optimising rules against naive 1/N on real data and found that, out of sample, none of them reliably won. The error in estimating expected returns and covariances cost more than optimising gained.

I replicated their comparison on the four of their datasets that come from Ken French's data library, with the tolerances the replication had to meet written down before any strategy code ran, and reran their simulation. I then ran the comparison forward to 2026: in the 261 months since the paper, no optimising rule beat naive 1/N significantly. Two Monte Carlo simulations of my own show that their conclusion survives fat-tailed returns and volatility that changes over time. The second also points to the next study: scaling the whole position with current volatility mattered more than knowing the covariances exactly.

The extension puts their question to a mandate closer to what an asset manager runs: a long-only portfolio that has to stay close to its benchmark under a weight bound, a turnover cap and an industry tilt. It asks whether the choice of covariance estimator still matters once those constraints bind, and what each constraint costs in tracking error. That part has not started.

The code goes up notebook by notebook at [github.com/ochofer/optimal-vs-naive-diversification](https://github.com/ochofer/optimal-vs-naive-diversification){: target="_blank"}.

Each project publishes its code in a public repository as its write-up goes up, so the analysis can be replicated.

For written analysis aimed at decision-makers, see the two DEMETRA policy briefs under [Publications](/publications/).
