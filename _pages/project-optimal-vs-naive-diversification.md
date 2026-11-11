---
layout: single
title: "Optimal versus naive diversification"
permalink: /projects/optimal-vs-naive-diversification/
author_profile: true
og_image: og-project-optimal-vs-naive.png
description: "Under an index-tracking mandate on French's 49 industries, five covariance estimators understate their own tracking error, by 22 to 61 per cent. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 Sharpe ratios that carry a band."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Portfolio construction</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/companion/industry_tilts_factor_exposures.html" target="_blank" rel="noopener"><i class="fas fa-calculator" aria-hidden="true"></i> Companion page</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-10.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_moduleA_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Second note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Every allocator meets the same question sooner or later: is it worth optimising a portfolio, or does naive 1/N, which splits the money equally across assets, do as well? DeMiguel, Garlappi and Uppal (2009)<sup id="ref-1"><a href="#note-1">1</a></sup> tested a range of optimising rules against naive 1/N on real data and found that, out of sample, none of them reliably won. The error in estimating expected returns and covariances cost more than optimising gained.

I replicated their comparison on four of the five datasets the paper takes from Ken French's library, against bands I fixed before writing the code: 29 of the 30 out-of-sample Sharpe ratios that carry a band of 0.03 reproduce within it, and all 30 turnover figures within 25 per cent. On the 261 months since the paper, none of the seven optimising rules earns a higher Sharpe ratio than 1/N at the 5 per cent level on any of the four datasets. Two Monte Carlo simulations of my own show that their conclusion survives fat-tailed returns and volatility that changes over time. The second also points to the next study: scaling the whole position with current volatility mattered more than knowing the covariances exactly.

I then asked their question of a long-only index-tracking mandate on French's 49 industries from 1979 to 2026. Each month, an optimiser I wrote in cvxpy finds the portfolio closest to a cap-weighted benchmark in ex-ante tracking error, under an active weight bound of 2 percentage points, a turnover cap of 2 per cent a month, a 50 per cent tilt against Coal, Oil and Utilities, the exclusion of tobacco and weapons, and a beta of one. The forecast comes from one of five covariance estimators: the sample covariance, Ledoit-Wolf shrinkage, a six-factor model and a principal-component model on three years of daily returns, and the sample covariance of 120 monthly returns. Under the mandate the estimators realise 84.7 to 95.8 basis points a year of tracking error, so the choice still matters by about a tenth, with the daily sample covariance and shrinkage the best. Every estimator understates its own tracking error, by 22 to 61 per cent. The tilt is associated with an active return of +2 to +7 basis points a year against a standard error of 12 to 13, which a factor attribution splits into factor exposures that cost 9 to 13 basis points and industry returns that paid 12 to 20.

Sixteen notebooks, every expectation written before its code, French's data downloaded at run time, 105 tests and an eleven-page note.

Version 2 turns the question round and asks what a budget of forecast tracking error buys when it is spent on purpose. Under the same mandate, the optimiser maximises the portfolio's exposure to value, profitability, investment and momentum, counted in beta units, within a budget of 75, 100 or 150 basis points a year, on nineteen paths over the same 566 months. A budget of 100 basis points bought about 0.0009 of beta per basis point of realised tracking error, three quarters or more of it in profitability and investment and almost none in momentum, and the realised tracking error ran 14 to 50 per cent above the budget on the daily estimators and further above it on the monthly one. Over the sample the four targeted factors contributed +27 to +36 basis points a year to the active return, on standard errors of 11 to 17, while the industries' own returns took back 31 to 37, so no path's active return is beyond two standard errors of zero. Holding the beta to the benchmark at one left an exposure of 0.012 to 0.015 to French's market factor, which the objective did not target. Seven expectations were written before the code, three were met and four were not, and each is reported with its arithmetic in the second note.<sup id="ref-2"><a href="#note-2">2</a>,&thinsp;</sup><sup id="ref-3"><a href="#note-3">3</a></sup>

## Notes

<ol class="notes">
<li id="note-1">DeMiguel, V., Garlappi, L. and Uppal, R. (2009). Optimal versus naive diversification: how inefficient is the 1/N portfolio strategy? <i>Review of Financial Studies</i> 22(5), 1915 to 1953. <a href="https://doi.org/10.1093/rfs/hhm075">https://doi.org/10.1093/rfs/hhm075</a></li>
<li id="note-2"><a href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_moduleA_2026-11.html">The factor objective under the mandate: what a budget of tracking error buys on French&rsquo;s 49 industries</a>, the second note, eleven pages.</li>
<li id="note-3">The seven expectations and their verdicts, in the <a href="https://github.com/ochofer/optimal-vs-naive-diversification#readme">README&rsquo;s module A table</a>.</li>
</ol>

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 listed companies to the 5,115 tracked assets they own. Of 19 apparent ownership changes checked by hand, 12 had no transaction behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.2/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
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
