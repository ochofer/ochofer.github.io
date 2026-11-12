---
layout: single
title: "Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample"
permalink: /projects/volatility-managed-portfolios/
author_profile: true
og_image: og-project-volatility-managed-portfolios.png?v=20261111c
description: "Volatility estimation and position sizing on Ken French's equity factors, backtested out of sample and without look-ahead, replicating Moreira and Muir (2017) and Cederburg, O'Doherty, Wang and Yan (2020). In build: its findings are stated when the study is complete."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Signal evaluation</p>

<p class="plinks"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Moreira and Muir (2017)<sup id="ref-1"><a href="#note-1">1</a></sup> found that scaling a factor's position each month by the inverse of its variance in the month before raised the factor's Sharpe ratio. Cederburg, O'Doherty, Wang and Yan (2020)<sup id="ref-2"><a href="#note-2">2</a></sup> found that the improvement is not there for an investor who has to estimate the scaling as the data arrive.

I am replicating both on Ken French's factors. The numbers the replication has to reproduce were typed from the journals before any code that judges them, and a test re-reads them digit by digit from the papers. Every expectation the replication and the test have to meet was written down and committed before any of them ran.

The study's own question is what the signal did in the months after Moreira and Muir's sample, May 2015 to August 2026, which neither paper could see. The study is in build, and its findings are stated when it is complete, with the write-up. Nothing on this page is a result.

The code is public on GitHub<sup id="ref-3"><a href="#note-3">3</a></sup> and goes up milestone by milestone.

## Notes

<ol class="notes">
<li id="note-1">Moreira, A. and Muir, T. (2017). Volatility-managed portfolios. <i>Journal of Finance</i> 72(4), 1611 to 1644. <a href="https://doi.org/10.1111/jofi.12513">https://doi.org/10.1111/jofi.12513</a></li>
<li id="note-2">Cederburg, S., O'Doherty, M. S., Wang, F. and Yan, X. S. (2020). On the performance of volatility-managed portfolios. <i>Journal of Financial Economics</i> 138(1), 95 to 117. <a href="https://doi.org/10.1016/j.jfineco.2020.04.015">https://doi.org/10.1016/j.jfineco.2020.04.015</a></li>
<li id="note-3"><a href="https://github.com/ochofer/volatility-managed-portfolios">volatility-managed-portfolios</a>, the repository on GitHub.</li>
</ol>

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Portfolio construction</p>
<p class="pcard__title"><a href="/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a></p>
<p class="pcard__text">Under an index-tracking mandate on French's 49 industries, five covariance estimators understate their own tracking error, by 22 to 61 per cent. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 Sharpe ratios that carry a band.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-10.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
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
<p class="pcard__kicker">Stock-level index tracking</p>
<p class="pcard__title"><a href="/projects/stock-level-tracking/">A point-in-time benchmark, a long-only mandate, and its performance attribution by sector</a></p>
<p class="pcard__text">A point-in-time S&amp;P 500 universe from CRSP and Compustat, a long-only mandate held close to its cap-weighted benchmark, and an attribution of its active return by sector. In build: its findings are stated when the study is complete.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Asset allocation</p>
<p class="pcard__title"><a href="/projects/rules-based-portfolio/">Rules-based portfolio</a></p>
<p class="pcard__text">Runs a real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/guide/guide.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Guide to the dashboard (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
