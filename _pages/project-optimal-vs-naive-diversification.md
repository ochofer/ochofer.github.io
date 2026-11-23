---
layout: single
title: "Optimal versus naive diversification"
permalink: /projects/optimal-vs-naive-diversification/
author_profile: true
og_image: og-project-optimal-vs-naive.png?v=20261111c
description: "Under a long-only index-tracking mandate on French's 49 industries, 1979 to 2026, each of five covariance estimators forecasts less tracking error than its portfolio realises: the realised active return is 22 to 61 per cent more volatile than forecast. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 out-of-sample Sharpe ratios within 0.03 of the published values."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Portfolio construction</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/companion/industry_tilts_factor_exposures.html" target="_blank" rel="noopener"><i class="fas fa-calculator" aria-hidden="true"></i> Companion page</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-10.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note on replication and tracking error (PDF)</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_moduleA_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note on factor exposure (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

This study asks whether the choice of covariance estimator, i.e., the method that estimates how returns move together, still matters when a long-only portfolio must follow an index under a mandate. The active return is the portfolio's return less the index's, and the tracking error is its standard deviation. On French's 49 industries from July 1979 to August 2026, each of the five covariance estimators tested forecasts less tracking error than its portfolio realises: the realised active return is 22 to 61 per cent more volatile than forecast.

The question comes from DeMiguel, Garlappi and Uppal (2009)<sup id="ref-1"><a href="#note-1">1</a></sup>, who find that no optimised portfolio does better than naive 1/N, i.e., the same weight on every asset, on returns the optimiser was not estimated on: the error in estimating expected returns and covariances is larger than the gain from optimising. This study replicates their comparison on Ken French's data and asks their question of the 49 industries under a mandate. In a third part the optimiser seeks the largest exposure to value, profitability, investment and momentum within a budget of forecast tracking error, each a factor, i.e., the return of a long-short portfolio sorted on that characteristic. The three parts are the *replication*, the *mandate* and the *factor objective*, the largest exposure to the four factors within that budget.

**The replication.** On the paper's sample, July 1963 to November 2004, 29 of the 30 out-of-sample Sharpe ratios tested are within 0.03 of the published values, where a Sharpe ratio is the mean return above the Treasury bill rate divided by its standard deviation, and out-of-sample means measured on months after those the rule was estimated on. All 30 figures for turnover, i.e., the share of the portfolio traded each month, are within 25 per cent. In the 261 months since the paper's sample, to August 2026, no optimising rule's Sharpe ratio exceeds 1/N's by a margin that is statistically significant at the 5 per cent level, on any of the four datasets, i.e., ten industry portfolios with the market, the three Fama-French factors, 20 portfolios sorted on size and book-to-market with the market, and the same 20 portfolios with four factors.

**The mandate.** The benchmark is the cap-weighted portfolio of French's 49 industries, i.e., each industry at its share of their total market value. From July 1979 to August 2026 an optimiser holds the long-only portfolio with the smallest forecast tracking error. Each industry stays within 2 percentage points of its benchmark weight, turnover is capped at 2 per cent a month, Coal, Oil and Utilities are held at no more than half their benchmark weight, tobacco and weapons are excluded, and the beta, i.e., the sensitivity of the portfolio's return to the benchmark's, is one. The forecast comes from one of the five covariance estimators: the sample covariance, Ledoit-Wolf shrinkage, a factor model and a principal-component model on three years of daily returns, and the sample covariance of 120 monthly returns.

A basis point is one hundredth of a percentage point. The portfolios realise 84.7 to 95.8 basis points a year of tracking error, and every forecast is below the realised figure. The factor and principal-component models realise 7 to 9 basis points a year more than the sample covariance and shrinkage. Each of these differences is statistically significant at the 5 per cent level on a paired test after Holm's correction across nine comparisons, a correction that sets a stricter threshold for each test when more than one is run together. The tilt, i.e., the lower weight on Coal, Oil and Utilities, is associated with an active return of +2 to +7 basis points a year, which is not statistically significant at the 5 per cent level, and the data rule out a cost of more than about 25 basis points a year.

**The factor objective.** With a budget of 100 basis points a year of forecast tracking error, the optimiser obtains 0.109 to 0.140 of combined exposure to the four factors, 74 to 85 per cent of it in profitability and investment. The realised tracking error is 19 to 50 per cent above the budget. The four factors contributed +26.7 to +35.5 basis points a year to the active return, which is statistically significant at the 5 per cent level. The residual, i.e., the part of the active return the factors do not explain, contributed −31 to −37 basis points a year, so the active return of no path, i.e., no pairing of estimator and budget, is statistically significant at that level.

The expectations of each part were written before its code ran, and the notebooks mark what was added after. French's data are downloaded at run time and never committed, and the code is public on GitHub<sup id="ref-2"><a href="#note-2">2</a></sup>.

## Terms

- **Active return**: the portfolio's return less the benchmark's.
- **Tracking error**: the standard deviation of the active return, as a figure for a year.
- **Covariance estimator**: the method that estimates how the assets' returns move together, from which the forecast tracking error is computed.
- **1/N**: the rule that holds every asset at the same weight and rebalances to it each month.
- **Factor**: the return of a long-short portfolio sorted on a company characteristic, e.g., profitability.
- **Sharpe ratio**: the mean return above the Treasury bill rate divided by its standard deviation.
- **Out-of-sample**: measured on months after those the rule was estimated on.
- **Benchmark**: the cap-weighted portfolio of the 49 industries, each at its share of their total market value.
- **Basis point**: one hundredth of a percentage point.
- **Holm's correction**: a rule that sets a stricter threshold for each test when more than one is run together, so that the chance of any false rejection across them stays at 5 per cent.

## Notes

<ol class="notes">
<li id="note-1">DeMiguel, V., Garlappi, L. and Uppal, R. (2009). Optimal versus naive diversification: how inefficient is the 1/N portfolio strategy? <i>Review of Financial Studies</i> 22(5), 1915 to 1953. <a href="https://doi.org/10.1093/rfs/hhm075">https://doi.org/10.1093/rfs/hhm075</a></li>
<li id="note-2"><a href="https://github.com/ochofer/optimal-vs-naive-diversification">optimal-vs-naive-diversification</a>, the repository on GitHub.</li>
</ol>

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, built from Global Energy Monitor's free tracker. Of 19 apparent ownership changes drawn at random and checked by hand, 12 had no corporate event behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.3/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
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
<p class="pcard__text">Rebuilds the S&amp;P 500 month by month from CRSP's list of members, at a tracking error of 11.5 basis points a year against CRSP's own return of the same list, and runs a long-only index-tracking mandate on it from 1999 to 2024, with its active return attributed by sector. The portfolios realise 78.9 to 83.6 basis points a year of tracking error, and each of four covariance estimators forecasts less: the realised active return is 48 to 85 per cent more volatile than forecast. Index changes require 11.4 per cent of the turnover of the portfolio built with Ledoit-Wolf shrinkage.</p>
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
