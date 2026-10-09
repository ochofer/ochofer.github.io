---
layout: single
title: "Optimal versus naive diversification"
permalink: /projects/optimal-vs-naive-diversification/
author_profile: true
og_image: og-project-optimal-vs-naive.png
description: "Under an index-tracking mandate on French's 49 industries, five covariance estimators understate their own tracking error, by 22 to 61 per cent. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 Sharpe ratios that carry a band."
---

<p class="pback"><a href="/projects/">&larr; All projects</a> &middot; Portfolio construction</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/companion/industry_tilts_factor_exposures.html" target="_blank" rel="noopener"><i class="fas fa-calculator" aria-hidden="true"></i> Companion page</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-10.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Every allocator meets the same question sooner or later: is it worth optimising a portfolio, or does naive 1/N, which splits the money equally across assets, do as well? DeMiguel, Garlappi and Uppal (2009) tested a range of optimising rules against naive 1/N on real data and found that, out of sample, none of them reliably won. The error in estimating expected returns and covariances cost more than optimising gained.

I replicated their comparison on four of the five datasets the paper takes from Ken French's library, against bands I fixed before writing the code: 29 of the 30 out-of-sample Sharpe ratios that carry a band of 0.03 reproduce within it, and all 30 turnover figures within 25 per cent. On the 261 months since the paper, one of 32 cells beats 1/N at the 5 per cent level. Two Monte Carlo simulations of my own show that their conclusion survives fat-tailed returns and volatility that changes over time. The second also points to the next study: scaling the whole position with current volatility mattered more than knowing the covariances exactly.

I then asked their question of a long-only index-tracking mandate on French's 49 industries from 1979 to 2026. Each month, an optimiser I wrote in cvxpy finds the portfolio closest to a cap-weighted benchmark in ex-ante tracking error, under an active weight bound of 2 percentage points, a turnover cap of 2 per cent a month, a 50 per cent tilt against Coal, Oil and Utilities, the exclusion of tobacco and weapons, and a beta of one. The forecast comes from one of five covariance estimators: the sample covariance, Ledoit-Wolf shrinkage, a six-factor model and a principal-component model on three years of daily returns, and the sample covariance of 120 monthly returns. Under the mandate the estimators realise 84.7 to 95.8 basis points a year of tracking error, so the choice still matters by about a tenth, with the daily sample covariance and shrinkage the best. Every estimator understates its own tracking error, by 22 to 61 per cent. The tilt is associated with an active return of +2 to +7 basis points a year against a standard error of 12 to 13, which a factor attribution splits into factor exposures that cost 9 to 13 basis points and industry returns that paid 12 to 20.

Thirteen notebooks, every expectation written before its code, French's data downloaded at run time, 92 tests and a ten-page note.
