---
layout: single
title: "Stock-level index tracking: a point-in-time benchmark, a long-only mandate, and its performance attribution by sector"
permalink: /projects/stock-level-tracking/
author_profile: true
og_image: og-project-stock-level-tracking.png?v=20261111c
description: "A point-in-time S&P 500 universe from CRSP and Compustat, a long-only mandate held close to its cap-weighted benchmark, and an attribution of its active return by sector. In build: the data layer is in place and checked, and nothing of the mandate is a result yet."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Stock-level index tracking</p>

<p class="plinks"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

A mandate that tracks an index is run in single stocks. Companies enter and leave the index, market capitalisations set the benchmark's weights, sectors bound what the portfolio may hold, and a delisted stock still has a last return. This study builds each of these from the source data and checks it before using it.

I build the S&P 500's membership month by month from CRSP's list of index members, with each stock's return, delisting return, market capitalisation and GICS sector, the last through CRSP's link to Compustat. The universe is checked against CRSP's own return, count and total value for the same list, and against Ken French's portfolios formed on size and momentum and on size and variance<sup id="ref-1"><a href="#note-1">1</a></sup>. Every gate and expectation these checks have to meet was written down and committed before any of them ran.

On that universe I then run a long-only mandate that holds close to the cap-weighted benchmark, under four covariance estimators from July 1999 to December 2024. Its turnover is split into the part that changes in index membership force and the part the optimiser chooses, and its active return is attributed by sector with the method of Brinson and Fachler (1985)<sup id="ref-2"><a href="#note-2">2</a></sup>. The study is in build. The data layer is in place and checked. The mandate and the attribution follow, and their results come at the last milestone with the write-up. Nothing on this page is a result.

The stock data are CRSP and Compustat, via Wharton Research Data Services, accessed through Queen Mary University of London, from an extraction of 28 September 2026. They are licensed, so the repository holds code, tests and aggregate results and none of the data. The code is public on GitHub<sup id="ref-3"><a href="#note-3">3</a></sup> and goes up milestone by milestone.

## Notes

<ol class="notes">
<li id="note-1"><a href="https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html">Kenneth French's data library</a>, the portfolios formed on size and momentum and on size and variance.</li>
<li id="note-2">Brinson, G. P. and Fachler, N. (1985). Measuring non-U.S. equity portfolio performance. <i>Journal of Portfolio Management</i> 11(3), 73 to 76. <a href="https://doi.org/10.3905/jpm.1985.409005">https://doi.org/10.3905/jpm.1985.409005</a></li>
<li id="note-3"><a href="https://github.com/ochofer/stock-level-tracking">stock-level-tracking</a>, the repository on GitHub.</li>
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
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Signal evaluation</p>
<p class="pcard__title"><a href="/projects/volatility-managed-portfolios/">Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample</a></p>
<p class="pcard__text">Volatility estimation and position sizing on Ken French's equity factors, backtested out of sample and without look-ahead, replicating Moreira and Muir (2017) and Cederburg, O'Doherty, Wang and Yan (2020). In build: the data and the signal are in place, and nothing in it is a result yet.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
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
