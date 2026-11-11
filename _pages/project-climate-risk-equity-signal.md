---
layout: single
title: "Climate risk as an equity signal"
permalink: /projects/climate-risk-equity-signal/
author_profile: true
og_image: og-project-climate-risk.png?v=20261111c
description: "An ownership graph linking 328 listed companies to the 5,115 tracked assets they own. Of 19 apparent ownership changes checked by hand, 12 had no transaction behind them."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Ownership and prices</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.2/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Companies own physical things. Power stations, pipelines, mines, cement works. Those things sit in places, and places have weather. The question was whether investors price the risk that weather damages those assets or interrupts what they produce.

The hard part was never the question, it was the join. Which company owns which asset, and what that company's shares did, are recorded in different places under different identifiers, and neither contains the other. So most of the work went into building that bridge and then trying to prove it wrong. The ownership graph is built from Global Energy Monitor's free tracker. 328 ownership entities resolve to the US and developed-Europe listed universe, 302 of them priceable, and all 328 together hold 5,115 tracked assets.

**One return test was specified and set aside before it ran**, on a power calculation published in the repository. A second, pre-registered, was run, and its result and the minimum detectable effect that makes it readable are reported in the data-quality note below.

**Most of what a vintage difference records is the file being edited.** I drew 19 apparent ownership changes at random from the 2,543 that two releases of the same database disagree on, and looked for the transaction behind each one in exchange filings, company statements and press releases. Twelve had none. The six that were real arrived 12 and 71 days late for the two recent and heavily covered deals, and 670 to 1,674 days late for the four that were older or smaller, so the recording error is selective, and a constant offset cannot repair it. Two undocumented choices, one the vendor's and one mine, each move a verdict I had committed to in writing before any script ran. What that costs a book: on the 191 firms with any coal or gas exposure, the rank correlation between the two releases is 0.73 under one blank-share convention and 0.77 under the other. The note, its code and its provenance records are public.

The data-acquisition layer is public and deliberately independent of any test. It was built to be reusable by whatever the analysis turned out to be, which is why setting that test aside required no change to it at all.

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Portfolio construction</p>
<p class="pcard__title"><a href="/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a></p>
<p class="pcard__text">Under an index-tracking mandate on French's 49 industries, five covariance estimators understate their own tracking error, by 22 to 61 per cent. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 Sharpe ratios that carry a band.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Signal evaluation</p>
<p class="pcard__title"><a href="/projects/volatility-managed-portfolios/">Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample</a></p>
<p class="pcard__text">A replication of Moreira and Muir's volatility-managed portfolios and of the real-time critique on Ken French's factors, then the months after the paper's sample. In build: the data and the signal are in place, and nothing in it is a result yet.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Stock-level index tracking</p>
<p class="pcard__title"><a href="/projects/stock-level-tracking/">A point-in-time benchmark, a long-only mandate, and its performance attribution by sector</a></p>
<p class="pcard__text">A point-in-time S&amp;P 500 universe from CRSP and Compustat, a long-only mandate held close to its cap-weighted benchmark, and an attribution of its active return by sector. In build: the data layer is in place and checked, and nothing of the mandate is a result yet.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Asset allocation</p>
<p class="pcard__title"><a href="/projects/rules-based-portfolio/">Rules-based portfolio</a></p>
<p class="pcard__text">Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
