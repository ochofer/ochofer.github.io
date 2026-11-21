---
layout: single
title: "Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample"
permalink: /projects/volatility-managed-portfolios/
author_profile: true
og_image: og-project-volatility-managed-portfolios.png?v=20261111c
description: "Volatility estimation and position sizing on Ken French's equity factors, replicating Moreira and Muir (2017) and the real-time critique of Cederburg, O'Doherty, Wang and Yan (2020). Scaled by the inverse of last month's realised variance, a factor's Sharpe ratio is higher than the original's by a margin that is statistically significant at the 5 per cent level for momentum alone when each of the six factors is tested on its own, and for no factor after Holm's correction for the six tests. In the 136 months after Moreira and Muir's sample no factor's difference is statistically significant, and the intervals are too wide to rule out the differences found on their sample."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Signal evaluation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/dashboard/B-Q_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/note/B-Q_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Moreira and Muir (2017)<sup id="ref-1"><a href="#note-1">1</a></sup> scale a factor's position each month by the inverse of its variance in the month before and measure what that adds as the scaled factor's alpha against the original. For three of the six factors replicated here, the market, momentum and profitability, their Table I gives a positive alpha more than two standard errors from zero. Cederburg, O'Doherty, Wang and Yan (2020)<sup id="ref-2"><a href="#note-2">2</a></sup> estimate in real time the weights that combine the scaled factor with the original. In their Table 5 the combination's Sharpe ratio is below that of the original for four of these six factors and above it for momentum, the one statistically significant difference, and for profitability.

I replicated both on Ken French's factors. The numbers the replication has to reproduce were typed from the journals before any code that judges them, and a test re-reads them digit by digit from the papers. Every expectation the replication and the test have to meet was written down and committed before any of them ran.

The study's own question is what the signal did in the 136 months after Moreira and Muir's sample, May 2015 to August 2026. Sharpe ratio differences are tested with Ledoit and Wolf's (2008)<sup id="ref-3"><a href="#note-3">3</a></sup> bootstrap.

The study supports a statement about the signal on French's six factors over these samples. Scaled, momentum's Sharpe ratio is 0.51 above the original's (0.07 to 0.96), which is statistically significant at the 5 per cent level when the factor is tested on its own (p 0.027) and not after Holm's correction for the six tests (p 0.16). The alphas of the market, momentum and profitability stay statistically significant at the 5 per cent level after the same correction. In the 136 months after the sample none of the twelve differences is statistically significant at the 5 per cent level, and for the six volatility-managed factors the intervals are too wide to rule out the differences found on Moreira and Muir's sample. At that length the test also rejects 2.0 per cent of the time where 5 is intended, so these months are weak evidence either way. The study holds no view on expected returns. The note states the limits in its last section.

The code is public on GitHub<sup id="ref-4"><a href="#note-4">4</a></sup>.

## Notes

<ol class="notes">
<li id="note-1">Moreira, A. and Muir, T. (2017). Volatility-managed portfolios. <i>Journal of Finance</i> 72(4), 1611 to 1644. <a href="https://doi.org/10.1111/jofi.12513">https://doi.org/10.1111/jofi.12513</a></li>
<li id="note-2">Cederburg, S., O'Doherty, M. S., Wang, F. and Yan, X. S. (2020). On the performance of volatility-managed portfolios. <i>Journal of Financial Economics</i> 138(1), 95 to 117. <a href="https://doi.org/10.1016/j.jfineco.2020.04.015">https://doi.org/10.1016/j.jfineco.2020.04.015</a></li>
<li id="note-3">Ledoit, O. and Wolf, M. (2008). Robust performance hypothesis testing with the Sharpe ratio. <i>Journal of Empirical Finance</i> 15(5), 850 to 859. <a href="https://doi.org/10.1016/j.jempfin.2008.03.002">https://doi.org/10.1016/j.jempfin.2008.03.002</a></li>
<li id="note-4"><a href="https://github.com/ochofer/volatility-managed-portfolios">volatility-managed-portfolios</a>, the repository on GitHub.</li>
</ol>

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
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, built from Global Energy Monitor's free tracker. Of 19 apparent ownership changes drawn at random and checked by hand, 12 had no corporate event behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.3/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
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
