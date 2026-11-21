---
layout: single
title: "Climate risk as an equity signal"
permalink: /projects/climate-risk-equity-signal/
author_profile: true
og_image: og-project-climate-risk.png?v=20261111c
description: "An ownership graph linking 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, built from Global Energy Monitor's free tracker. Of 19 apparent ownership changes drawn at random and checked by hand, 12 had no corporate event behind them."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Ownership and prices</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.3/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Companies own physical things. Power stations, pipelines, mines, cement works. Those things sit in places, and places have weather. The question was whether investors price the risk that weather damages those assets or interrupts what they produce.

The hard part was never the question, it was the join. Which company owns which asset, and what that company's shares did, are recorded in different places under different identifiers, and neither contains the other. So most of the work went into building that bridge and then trying to prove it wrong. The ownership graph is built from Global Energy Monitor's free tracker. It links 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, an asset with two owners among them counted once for each.

**One return test was specified and set aside before it ran**, on a power calculation published in the repository. A second was run under a rule written in the header of its script, and the data-quality note below reports it.

**Of 19 recorded ownership changes checked by hand, 12 had no corporate event behind them.** Two releases of the same database differ on 12,717 ownership edges, and the study classes 2,543 of them as restatement, a link removed or a share revised. I drew 19 of those 2,543, in proportion to the three kinds of restatement, and looked for the transaction behind each one in exchange filings, company statements and press releases. Twelve had none. How an empty ownership share is read, a choice of mine that the data does not document, moves the rank correlation of firms' attributable coal and gas capacity between the two releases from 0.91 to 0.98 on the 171 panel firms, either side of the 0.95 the study takes as its line. The note, its code and its provenance records are public.

The data-acquisition layer is public and deliberately independent of any test. It was built to be reusable by whatever the analysis turned out to be, which is why setting that test aside required no change to it at all.

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Portfolio construction</p>
<p class="pcard__title"><a href="/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a></p>
<p class="pcard__text">Under an index-tracking mandate on French's 49 industries, five covariance estimators understate their own tracking error over 1979 to 2026: the realised active return is 22 to 61 per cent more volatile than forecast. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 Sharpe ratios that carry a band, 26 of 27 with the value-weighted market counted once.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-10.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Signal evaluation</p>
<p class="pcard__title"><a href="/projects/volatility-managed-portfolios/">Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample</a></p>
<p class="pcard__text">Volatility estimation and position sizing on Ken French's equity factors, replicating Moreira and Muir (2017) and the real-time critique of Cederburg, O'Doherty, Wang and Yan (2020). Scaled by the inverse of last month's realised variance, a factor's Sharpe ratio is higher than the original's by a margin that is statistically significant at the 5 per cent level for momentum alone when each of the six factors is tested on its own, and for no factor after Holm's correction for the six tests. In the 136 months after Moreira and Muir's sample no factor's difference is statistically significant, and the intervals are too wide to rule out the differences found on their sample.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/dashboard/B-Q_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/note/B-Q_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Stock-level index tracking</p>
<p class="pcard__title"><a href="/projects/stock-level-tracking/">A point-in-time benchmark, a long-only mandate, and its performance attribution by sector</a></p>
<p class="pcard__text">A point-in-time S&amp;P 500 universe from CRSP and Compustat, a long-only mandate held close to its cap-weighted benchmark, and an attribution of its active return by sector. Under the mandate, simulated from 1999 to 2024, four covariance estimators realise 78.9 to 83.6 basis points a year of tracking error, and each forecast understates it: the realised active return is 48 to 85 per cent more volatile than forecast. Index changes force 11.4 per cent of the turnover on the Ledoit-Wolf estimator, and no estimator's mean active return is statistically significant at the 5 per cent level, which over these 306 months would take one of about 35 basis points a year.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/stock-level-tracking/dashboard/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/stock-level-tracking/note/stock-level-tracking_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Asset allocation</p>
<p class="pcard__title"><a href="/projects/rules-based-portfolio/">Rules-based portfolio</a></p>
<p class="pcard__text">Runs a real-money portfolio under rules published before the first order, with every later change dated in the repository: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/guide/guide.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Guide to the dashboard (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
