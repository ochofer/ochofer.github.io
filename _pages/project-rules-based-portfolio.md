---
layout: single
title: "Rules-based portfolio"
permalink: /projects/rules-based-portfolio/
author_profile: true
og_image: og-project-rules-based-portfolio.png?v=20261105
description: "Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks."
---

<p class="pback">Portfolio in practice &middot; Asset allocation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/guide/guide.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Guide to the dashboard (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.

The portfolio holds a global equity ETF and a euro government bond ETF. Its mandate, a written statement of what the portfolio is for, and the ten rules that say how it is run were written down on 7 October 2026, together with the choice of the two funds, before the first purchase on 8 October. They were saved that day as a dated version in the public repository, so any later change to them is visible. On the fifth of each month, the cycle day, a program checks the rules against the positions, proposes the orders the rules call for and writes a report before any order is placed. Every departure from the rules is kept in a register. A monthly note follows each cycle day, and a quarterly report follows each quarter, the first in January 2027.

The split between the two asset classes, that is, how much of the portfolio is held in shares and how much in government bonds, is set by a limit on risk. The mandate asks for the highest long-run growth over five to ten years within a worst fall of about one third, the worst fall being the largest drop in value from a previous high to a later low. The split was chosen with a test on past market data: on monthly euro returns from February 1999 to December 2025, built from Kenneth French's market returns and ECB series, splits from 40 to 100 per cent in shares were run under the same rule for returning to the target as the portfolio uses, and 70 per cent in shares is the largest whose worst fall stayed within 35 per cent, at 34.7 per cent from August 2000 to March 2003. The test uses index data from before the portfolio existed, so its figures show how each split would have behaved on that history and are not results of the portfolio itself. Anyone can rerun it from the code on GitHub.

The dashboard, rebuilt every Monday and on each cycle day, draws every figure from a committed table: the weights and the drift, the costs by source, the look-through to the countries, sectors, currencies and issuers inside both funds, the equity fund's factor loadings, and an estimate of the portfolio's volatility and one-month value at risk on index returns at the look-through weights. Two reference portfolios computed from the same contributions without costs show the implementation cost. The dashboard shows the portfolio's return, but it is not offered as proof that the rules are good. Over a few years, markets rise and fall by so much that a good or a bad result can come from luck alone, so a record this short cannot tell good rules from bad ones.

The portfolio uses no optimiser, that is, no program that works out the weights from estimates of how much each fund will return and how much its price will move. It holds no view, that is, no forecast that one market will do better than another, and follows no signal, that is, no indicator such as a recent price trend or a valuation measure that would move money between the two funds over time. Its benchmark is the blend of its two funds' own indices at 70 and 30 per cent, the portfolio the rules aim at, so the difference to it measures the cost of running the portfolio and not a bet against it. No single market index is set as its benchmark, as one would be for a fund manager. The expected return of shares and of bonds cannot be estimated from the data closely enough to choose between splits, which is why the limit sets the split, a result that DeMiguel, Garlappi and Uppal established<sup id="ref-1"><a href="#note-1">1</a></sup> and the replication study on this site confirms.<sup id="ref-2"><a href="#note-2">2</a></sup> The question why the portfolio does not simply hold the S&P 500 is answered on the dashboard's Method view,<sup id="ref-3"><a href="#note-3">3</a></sup> with the allocation test rerun on the US market in euro and a running comparison, without costs, against the S&P 500 ETF the selection criteria of the rules pick: the global fund already holds the index's companies at about two thirds of its weight, and a weight on one country above its share of the world is a view the rules do not take.

## Notes

<ol class="notes">
<li id="note-1">DeMiguel, V., Garlappi, L. and Uppal, R. (2009). Optimal versus naive diversification: how inefficient is the 1/N portfolio strategy? <i>Review of Financial Studies</i> 22(5), 1915 to 1953. <a href="https://doi.org/10.1093/rfs/hhm075">https://doi.org/10.1093/rfs/hhm075</a></li>
<li id="note-2"><a href="https://www.carlohofer.com/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a>, the project page.</li>
<li id="note-3">The section <a href="https://www.carlohofer.com/rules-based-portfolio/#method-not-done">“What the portfolio does not do, and why”</a> on the dashboard.</li>
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
