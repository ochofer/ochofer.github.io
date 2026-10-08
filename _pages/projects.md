---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
og_image: og-projects.png?v=20261004
og_title: "Quantitative investment projects: public data, public code"
description: "An ownership graph of 328 listed companies holding 5,115 tracked assets, public with its code. I checked 19 apparent ownership changes across two database releases by hand. Twelve had no corporate event behind them."
---

{% include base_path %}

Alongside my other academic research, I also work on quantitative questions in financial markets. These are self-directed research exercises using public data. Each write-up states the question, the data, the method, and the result, including where the result was null, and links to the code so the analysis can be reproduced.

## Portfolio construction

**Optimal versus naive diversification.** Every allocator meets the same question sooner or later: is it worth optimising a portfolio, or does naive 1/N, which splits the money equally across assets, do as well? DeMiguel, Garlappi and Uppal (2009) tested a range of optimising rules against naive 1/N on real data and found that, out of sample, none of them reliably won. The error in estimating expected returns and covariances cost more than optimising gained.

I replicated their comparison on four of the five datasets the paper takes from Ken French's library, against bands I fixed before writing the code: 29 of the 30 out-of-sample Sharpe ratios that carry a band of 0.03 reproduce within it, and all 30 turnover figures within 25 per cent. On the 261 months since the paper, one of 32 cells beats 1/N at the 5 per cent level. Two Monte Carlo simulations of my own show that their conclusion survives fat-tailed returns and volatility that changes over time. The second also points to the next study: scaling the whole position with current volatility mattered more than knowing the covariances exactly.

I then asked their question of a long-only index-tracking mandate on French's 49 industries from 1979 to 2026. Each month, an optimiser I wrote in cvxpy finds the portfolio closest to a cap-weighted benchmark in ex-ante tracking error, under an active weight bound of 2 percentage points, a turnover cap of 2 per cent a month, a 50 per cent tilt against Coal, Oil and Utilities, the exclusion of tobacco and weapons, and a beta of one. The forecast comes from one of five covariance estimators: the sample covariance, Ledoit-Wolf shrinkage, a six-factor model and a principal-component model on three years of daily returns, and the sample covariance of 120 monthly returns. Under the mandate the estimators realise 84.7 to 95.8 basis points a year of tracking error, so the choice still matters by about a tenth, with the daily sample covariance and shrinkage the best. Every estimator understates its own tracking error, by 22 to 61 per cent. The tilt is associated with an active return of +2 to +7 basis points a year against a standard error of 12 to 13, which a factor attribution splits into factor exposures that cost 9 to 13 basis points and industry returns that paid 12 to 20.

Thirteen notebooks, every expectation written before its code, French's data downloaded at run time, 92 tests and a ten-page note. The code is at [github.com/ochofer/optimal-vs-naive-diversification](https://github.com/ochofer/optimal-vs-naive-diversification){: target="_blank"}, and the dashboard, the companion page and the note open at [carlohofer.com/optimal-vs-naive-diversification](https://www.carlohofer.com/optimal-vs-naive-diversification/){: target="_blank"}.

## Ownership and prices

**Climate risk as an equity signal.** Companies own physical things. Power stations, pipelines, mines, cement works. Those things sit in places, and places have weather. The question was whether investors price the risk that weather damages those assets or interrupts what they produce.

The hard part was never the question, it was the join. Which company owns which asset, and what that company's shares did, are recorded in different places under different identifiers, and neither contains the other. So most of the work went into building that bridge and then trying to prove it wrong. The ownership graph is built from Global Energy Monitor's free tracker. 328 ownership entities resolve to the US and developed-Europe listed universe, 302 of them priceable, and all 328 together hold 5,115 tracked assets.

**One return test was specified and set aside before it ran**, on a power calculation published in the repository. A second, pre-registered, was run, and its result and the minimum detectable effect that makes it readable are reported in the data-quality note below.

**Most of what a vintage difference records is the file being edited.** I drew 19 apparent ownership changes at random from the 2,543 that two releases of the same database disagree on, and looked for the transaction behind each one in exchange filings, company statements and press releases. Twelve had none. The six that were real arrived 12 and 71 days late for the two recent and heavily covered deals, and 670 to 1,674 days late for the four that were older or smaller, so the recording error is selective, and a constant offset cannot repair it. Two undocumented choices, one the vendor's and one mine, each move a verdict I had committed to in writing before any script ran. What that costs a book: on the 191 firms with any coal or gas exposure, the rank correlation between the two releases is 0.73 under one blank-share convention and 0.77 under the other. The note, its code and its provenance records are public.

[Read the note](https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.2/what-a-vintage-difference-measures.pdf){: target="_blank"} (PDF), or find it under [Publications](/publications/).

The data-acquisition layer is public and deliberately independent of any test: [github.com/ochofer/paper1-hazard-exposure-data](https://github.com/ochofer/paper1-hazard-exposure-data){: target="_blank"}. It was built to be reusable by whatever the analysis turned out to be, which is why setting that test aside required no change to it at all.

## Asset allocation

**Rules-based portfolio.** I run a real-money portfolio under written rules: 70 per cent in a global equity ETF and 30 per cent in a euro government bond ETF. The mandate's risk limit, a worst fall of about one third, sets the split: on monthly euro returns from 1999 to 2025, 70 per cent is the largest equity weight whose worst fall stayed within 35 per cent (34.7 per cent, from August 2000 to March 2003). On each monthly cycle day the top-up buys the sleeve furthest below its target weight, and if the equity weight is outside the band from 65 to 75 per cent the portfolio is brought back to 70/30. The rules were fixed and tagged on 7 October 2026, before the first purchases the next day. A program computes the record from the private ledger, and a dashboard draws it: the orders and their costs, the drift of the weights, the rebalancing the rules produce, the look-through of both ETFs and the factor exposures of the equity ETF.

The mandate, the test and the rules are at [github.com/ochofer/rules-based-portfolio](https://github.com/ochofer/rules-based-portfolio){: target="_blank"}. The dashboard, rebuilt every Monday and on each cycle day, opens at [carlohofer.com/rules-based-portfolio](https://www.carlohofer.com/rules-based-portfolio/){: target="_blank"}.

## Code and other writing

Each project publishes its code in a public repository as its write-up goes up, so the analysis can be replicated.

For written analysis aimed at decision-makers, see the two DEMETRA policy briefs under [Publications](/publications/).
