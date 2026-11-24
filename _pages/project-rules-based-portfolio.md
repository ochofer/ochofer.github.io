---
layout: single
title: "Rules-based portfolio"
permalink: /projects/rules-based-portfolio/
author_profile: true
og_image: og-project-rules-based-portfolio.png?v=20261111c
description: "Runs a real-money portfolio under rules published before the first order, with every later change dated in the repository: two UCITS ETFs at 70/30."
---

<p class="pback">Portfolio in practice &middot; Asset allocation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/guide/guide.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Guide to the dashboard (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

I run a real-money portfolio under written rules: 70 per cent in a global equity ETF and 30 per cent in a euro government bond ETF, funded by a starting amount and a fixed monthly top-up. The mandate states the objective, the highest long-run growth over five to ten years, and the risk limit, a worst fall of about one third, i.e., the largest fall in value from a previous peak to a later low. The split between the two ETFs is derived from that limit by a test on monthly data from 1999 to 2025, the *allocation test*. The rules were fixed before the first order of 8 October 2026 and are tagged `rules-v1.0` in the repository. Rule 11, added by amendment and tagged `rules-v1.1`, moves the target weights with the allocation test from the cycle day of 5 January 2027.

**The monthly cycle.** On the cycle day, the 5th of each month or the first trading day after it, a program computes the weights from the record of contributions and orders, proposes the orders the rules require, and writes a cycle report, i.e., each rule that bears on the proposed orders with its figure and a pass or a fail, before any order is placed. The top-up is spent on the sleeve, i.e., the part of the portfolio held in one ETF, furthest below its target weight. If the equity weight is then outside the band, five points either side of the equity target weight, 65 to 75 per cent at rule 1's weights, the portfolio goes back to the target weights the same day. Every order placed or left unplaced other than as the rules require is a departure, and the register lists each one. A rule changes only by a dated amendment, which applies from the first cycle day at least 30 days after it is committed. A monthly note follows each cycle day and a quarterly report each quarter.

**The split.** On monthly euro returns from February 1999 to December 2025, the allocation test measures each split's worst fall. Its deciding series for equity, i.e., the one that sets the split, is Kenneth French's market returns for five regions at the equity ETF's weights by region of 13 November 2026, and on it 70/30's worst fall is 34.55 per cent, 0.45 points inside the limit of 35 per cent. The test reads "about one third" as at most 35 per cent. On two MSCI series the same split falls 35.75 to 36.53 per cent, so across the two sources the test does not decide between 70/30 and 65/35. On the deciding series 65/35 is also the result if the limit is read as one third, 33.3 per cent, or if the bond's maturity is five years in place of the test's seven. Rule 1 sets the target at 70/30. The figures show how each split behaved on that history and are not results of the portfolio.

**The dashboard.** Rebuilt every Monday and on each cycle day from committed tables, it gives the weights and their drift, the costs by source, the look-through, i.e., the countries, sectors, currencies and issuers inside both ETFs, and the portfolio's estimated volatility, value at risk and expected shortfall over one month, estimated on index returns. Two reference portfolios computed from the same contributions without costs give the implementation cost, and the Comparisons part sets the record beside portfolios that receive the same contributions on the same days. A record of five to ten years is too short to show that one set of rules is better than another, so the returns are not offered as evidence for the rules.

The weights come from the rules alone, with no optimiser, view or signal. The portfolio's benchmark is the index blend, i.e., the indices of its two ETFs at the target weights, so the difference to it comes from implementing the rules: the funds' costs and tracking differences, the drift inside the band, cash waiting for the cycle day, and trading. Over the allocation test's 27 years the gap in growth per year, i.e., the compound annual return, between the 100/0 and 40/60 splits is 2.9 points, with a 95 per cent interval from −2.1 to +7.6 points. The history therefore does not fix even the sign of the gap, and the risk limit sets the split. The dashboard's Method view<sup id="ref-1"><a href="#note-1">1</a></sup> gives the reasons in full, among them why the portfolio does not hold the S&P 500 alone. Euro amounts, units and the broker's statements are kept private and never committed, and the code is public on GitHub<sup id="ref-2"><a href="#note-2">2</a></sup>.

## Terms

- **Worst fall**: the largest fall in value from a previous peak to a later low, with contributions removed.
- **Split**: a pair of target weights, written equity/bonds, e.g., 70/30.
- **Target weight**: the weight the rules aim for in a sleeve.
- **Cycle day**: the 5th of each month, or the first trading day after it, on which the rules are applied.
- **Sleeve**: the part of the portfolio held in one ETF.
- **Band**: the interval five points either side of the equity target weight, from 65 to 75 per cent at the target weights of rule 1.
- **Departure**: an order placed, or left unplaced, other than as the rules require.
- **Look-through**: the portfolio's exposure to the securities inside the two ETFs.
- **Value at risk**: the loss over one month at 95 per cent at today's weights.
- **Expected shortfall**: the mean loss at or beyond the value at risk.
- **Implementation cost**: the difference between the portfolio and a reference portfolio that follows the same rules without costs.
- **Index blend**: the indices of the two ETFs at the target weights, the portfolio's benchmark.

## Notes

<ol class="notes">
<li id="note-1">The section <a href="https://www.carlohofer.com/rules-based-portfolio/#method-not-done">“What the portfolio does not do, and why”</a> on the dashboard.</li>
<li id="note-2"><a href="https://github.com/ochofer/rules-based-portfolio">rules-based-portfolio</a>, the repository on GitHub.</li>
</ol>

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Portfolio construction</p>
<p class="pcard__title"><a href="/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a></p>
<p class="pcard__text">Under a long-only index-tracking mandate on French's 49 industries, 1979 to 2026, each of five covariance estimators forecasts less tracking error than its portfolio realises: the realised active return is 22 to 61 per cent more volatile than forecast. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 out-of-sample Sharpe ratios it tests within 0.03 of the published values, 26 of 27 with the value-weighted market counted once.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-10.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, built from Global Energy Monitor's free tracker. Of 19 apparent ownership changes drawn at random and checked by hand, 12 had no corporate event behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.4/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Signal evaluation</p>
<p class="pcard__title"><a href="/projects/volatility-managed-portfolios/">Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample</a></p>
<p class="pcard__text">Volatility estimation and position sizing on Ken French's equity factors, replicating Moreira and Muir (2017) and the real-time critique of Cederburg, O'Doherty, Wang and Yan (2020). Scaled by the inverse of last month's realised variance, a factor's Sharpe ratio is higher than the original's by a margin that is statistically significant at the 5 per cent level for momentum alone when each of the six factors is tested on its own, and for no factor after Holm's correction for the six tests. In the 136 months after Moreira and Muir's sample no factor's difference is statistically significant, and for the six volatility-managed factors the intervals are too wide to rule out the differences found on their sample.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/dashboard/B-Q_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/note/B-Q_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Stock-level index tracking</p>
<p class="pcard__title"><a href="/projects/stock-level-tracking/">A point-in-time benchmark, a long-only mandate, and its performance attribution by sector</a></p>
<p class="pcard__text">Rebuilds the S&amp;P 500 month by month from CRSP's list of members, at a tracking error of 11.5 basis points a year from 1926 to 2024 against CRSP's own return of the same list, and runs a long-only index-tracking mandate on it from 1999 to 2024, with its active return attributed by sector. The portfolios realise 78.9 to 83.6 basis points a year of tracking error, and each of four covariance estimators forecasts less: the realised active return is 48 to 85 per cent more volatile than forecast. Index changes require 11.4 per cent of the turnover of the portfolio built with Ledoit-Wolf shrinkage.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/stock-level-tracking/dashboard/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/stock-level-tracking/note/stock-level-tracking_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Return prediction</p>
<p class="pcard__title"><a href="/projects/ml-return-prediction-backtest-overfitting/">Machine learning on the S&amp;P 500's members, corrected for overfitting</a></p>
<p class="pcard__text">Forecasts of each S&amp;P 500 member's return over the next month from twelve characteristics built from CRSP and Compustat, by six models from least squares to a neural network, out of sample from 2006 to 2024. The study follows the method of Gu, Kelly and Xiu (2020), reduced to the index's members, and corrects the best result for overfitting, that is, for having tried many versions and kept the best one. In build: its findings are stated when the study is complete.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/ml-return-prediction-backtest-overfitting" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
