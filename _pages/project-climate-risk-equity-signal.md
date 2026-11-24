---
layout: single
title: "Climate risk as an equity signal"
permalink: /projects/climate-risk-equity-signal/
author_profile: true
og_image: og-project-climate-risk.png?v=20261111c
description: "An ownership graph linking 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, built from Global Energy Monitor's free tracker. Of 19 apparent ownership changes drawn at random and checked by hand, 12 had no corporate event behind them."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Ownership and prices</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.4/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Companies own physical assets, e.g., power stations, pipelines, mines and cement works, and those assets sit in places whose weather varies. The question these data are built for is whether investors price the risk that weather damages those assets or interrupts what they produce, i.e., whether companies holding more exposed assets earn different returns once the known drivers of returns are controlled for. This project builds and audits the data for that question in two parts, the *ownership graph* and the *note*. Of 19 restatements, i.e., ownership links removed or shares revised between two releases of the data, drawn at random and checked by hand, 12 had no corporate event behind them.

The project tests no hypothesis that this risk is priced. A power calculation set the planned return test, a cross-sectional Fama-MacBeth design, aside. One return comparison was run, under a rule set in its script before the run: the spread between the fifths of the panel with the most and the least attributable fossil capacity, computed on each of two releases with ownership data from late in or after the return window, to measure whether the spread moves with the release. The note reports its result with the smallest effect the data could detect.

**The ownership graph.** Which company owns which asset and what that company's shares did are recorded in different sources under different identifiers, and neither holds the other's key. Built from Global Energy Monitor's free tracker, the graph links 328 ownership entities in the US and developed Europe, 302 of them listed and priceable, to 5,115 asset holdings. An ownership entity is an owner as Global Energy Monitor records it, before any matching, priceable means that its shares resolve to a tradeable listing in the price panel, and an asset owned by two of the 328 counts as two holdings. The price panel of the 302 companies and two reference series passes 16 of 16 integrity checks.

**The note.** In the note, *What a vintage difference measures*, the changes between two releases, i.e., two dated files, of the ownership database are checked by hand. The two releases differ on 12,717 ownership edges, i.e., links between an owner and an asset, and 2,543 of them are classed as restatements. Of 19 restatements drawn at random, in proportion to their three kinds, and checked against exchange filings, company statements and press releases, 12 had no corporate event behind them. How an empty ownership share is read, a choice the data do not document, moves the rank correlation of firms' attributable coal and gas capacity between the two releases from 0.91 to 0.98 on the 171 panel firms, either side of the 0.95 the note takes as its line.

The hazard study itself is closed: the hazard measure is not built and not scheduled, and nothing in the repository depends on it. The ownership data are Global Energy Monitor's, under CC BY 4.0. The share prices are licensed and not redistributed, and the repository publishes the code that fetches them with a manifest of every file's hash. The code is public on GitHub<sup id="ref-1"><a href="#note-1">1</a></sup>.

## Terms

- **Restatement**: an edge removed or a share revised between two releases.
- **Release**: one dated file of the ownership tracker, identified by its file name and hash.
- **Ownership entity**: an owner as Global Energy Monitor records it, before any matching.
- **Priceable**: resolved to a tradeable listing in the price panel.
- **Asset holding**: one owner's stake in one asset, so an asset with two owners counts twice.
- **Ownership edge**: a link between an owner and an asset in one release of the database.
- **Rank correlation**: the correlation of two rankings of the same firms, 1 when they agree exactly.

## Notes

<ol class="notes">
<li id="note-1"><a href="https://github.com/ochofer/paper1-hazard-exposure-data">paper1-hazard-exposure-data</a>, the repository on GitHub.</li>
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
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Asset allocation</p>
<p class="pcard__title"><a href="/projects/rules-based-portfolio/">Rules-based portfolio</a></p>
<p class="pcard__text">Runs a real-money portfolio under rules published before the first order, with every later change dated in the repository: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/guide/guide.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Guide to the dashboard (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
