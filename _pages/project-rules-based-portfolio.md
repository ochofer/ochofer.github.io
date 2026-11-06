---
layout: single
title: "Rules-based portfolio"
permalink: /projects/rules-based-portfolio/
author_profile: true
og_image: og-project-rules-based-portfolio.png?v=20261105
description: "Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks."
---

<p class="pback"><a href="/projects/">&larr; All projects</a> &middot; Asset allocation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.

The portfolio holds a global equity ETF and a euro government bond ETF. The mandate, the ten rules and the choice of the two funds were written and tagged on 7 October 2026, before the first purchase on 8 October. On the fifth of each month a program checks the rules against the positions, proposes the orders the rules call for and writes a report before any order is placed. Every departure from the rules is kept in a register. A monthly note follows each cycle day, and a quarterly report follows each quarter, the first in January 2027.

The split is set by the risk limit. The mandate asks for the highest long-run growth over five to ten years within a worst fall of about one third. On monthly euro returns from February 1999 to December 2025, built from Kenneth French's market returns and ECB series, 70 per cent equity is the largest target weight whose worst fall under the band rule stayed within 35 per cent: 34.7 per cent from August 2000 to March 2003. The test runs on index history and says nothing about the record itself. Anyone can rerun it from the repository.

The dashboard, rebuilt every Monday and on each cycle day, draws every figure from a committed table: the weights and the drift, the costs by source, the look-through to the countries, sectors, currencies and issuers inside both funds, the equity fund's factor loadings, and an estimate of the portfolio's volatility and one-month value at risk on index returns at the look-through weights. Two reference portfolios computed from the same contributions without costs show the implementation cost. No return is offered as evidence for the rules: with a book this size and a record of a few years, a return cannot show whether the rules are good.

The portfolio runs no optimiser, holds no view, carries no signal and is measured against no index. The expected return of each sleeve cannot be estimated from the data closely enough to choose between splits, which is why the limit sets the split, a result that DeMiguel, Garlappi and Uppal established<sup id="ref-1"><a href="#note-1">1</a></sup> and the replication study on this site confirms.<sup id="ref-2"><a href="#note-2">2</a></sup> The question why the portfolio does not simply hold the S&P 500 is answered on the dashboard's Method view,<sup id="ref-3"><a href="#note-3">3</a></sup> with the allocation test rerun on the US market in euro and a running comparison, without costs, against the S&P 500 ETF the selection criteria of the rules pick: the global fund already holds the index's companies at about two thirds of its weight, and a weight on one country above its share of the world is a view the rules do not take.

## Notes

<ol class="notes">
<li id="note-1">DeMiguel, V., Garlappi, L. and Uppal, R. (2009). Optimal versus naive diversification: how inefficient is the 1/N portfolio strategy? <i>Review of Financial Studies</i> 22(5), 1915 to 1953. <a href="https://doi.org/10.1093/rfs/hhm075">https://doi.org/10.1093/rfs/hhm075</a></li>
<li id="note-2">Optimal versus naive diversification: <a href="https://www.carlohofer.com/projects/optimal-vs-naive-diversification/">https://www.carlohofer.com/projects/optimal-vs-naive-diversification/</a></li>
<li id="note-3">The section “What the portfolio does not do, and why” on the dashboard: <a href="https://www.carlohofer.com/rules-based-portfolio/#method-not-done">https://www.carlohofer.com/rules-based-portfolio/#method-not-done</a></li>
</ol>

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
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 listed companies to the 5,115 tracked assets they own. Of 19 apparent ownership changes checked by hand, 12 had no transaction behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.2/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
