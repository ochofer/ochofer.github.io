---
layout: single
title: "Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample"
permalink: /projects/volatility-managed-portfolios/
author_profile: true
og_image: og-project-volatility-managed-portfolios.png?v=20261111c
description: "Volatility estimation and position sizing on Ken French's equity factors, replicating Moreira and Muir (2017) and the real-time critique of Cederburg, O'Doherty, Wang and Yan (2020). Scaled by the inverse of last month's realised variance, a factor's Sharpe ratio is higher than the original's by a margin that is statistically significant at the 5 per cent level for momentum alone when each of the six factors is tested on its own, and for no factor after Holm's correction for the six tests. In the 136 months after Moreira and Muir's sample no factor's difference is statistically significant, and for the six volatility-managed factors the intervals are too wide to rule out the differences found on their sample."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Signal evaluation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/dashboard/B-Q_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/volatility-managed-portfolios/note/B-Q_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

A factor is the return of a long-short portfolio sorted on a company characteristic, or the market's return above the Treasury bill rate. This study compares each of Ken French's six factors, i.e., the market, size, value, momentum, profitability and investment, with the same factor scaled each month by the inverse of its realised variance in the month before, i.e., computed from its daily returns in that month, with data to August 2026. The Sharpe ratio is the mean return above the Treasury bill rate divided by its standard deviation. On Moreira and Muir's sample, which ends in April 2015, the scaled factor held in the original's place has a Sharpe ratio higher by a margin that is statistically significant at the 5 per cent level for momentum alone, tested on its own, and for no factor after Holm's correction, i.e., a stricter threshold for each test when the six are tested together.

Moreira and Muir (2017)<sup id="ref-1"><a href="#note-1">1</a></sup> scale factors in this way and find a positive alpha, i.e., a mean return that the unscaled factor does not explain, for five of the six factors studied here, more than two standard errors from zero for the market, momentum and profitability. Cederburg, O'Doherty, Wang and Yan (2020)<sup id="ref-2"><a href="#note-2">2</a></sup> estimate in real time how an investor would combine the scaled and the original factor, and find, for the six factors studied here, little gain outside momentum. The study has three parts, the *replications* of both papers and of the scaled momentum of Barroso and Santa-Clara (2015)<sup id="ref-3"><a href="#note-3">3</a></sup>, the *two tests* on Moreira and Muir's sample, of the alpha and of the difference in Sharpe ratio, the second with the bootstrap of Ledoit and Wolf (2008)<sup id="ref-4"><a href="#note-4">4</a></sup>, and the *months after the sample*, the 136 months from May 2015 to August 2026.

**The replications.** Moreira and Muir's Table I reproduces for 6 of 6 factors: the market's alpha is 4.93 per cent a year against the paper's 4.86. Barroso and Santa-Clara's scaled momentum reproduces in 4 of 4 comparisons, and Cederburg et al.'s results in 22 of 24. Both misses are on RMW, the profitability factor, whose mean in French's current file differs from the paper's, so French has most likely revised it since.

**The two tests.** The alphas of the market, momentum and RMW are statistically significant at the 5 per cent level after Holm's correction for the six tests. For momentum, the scaled factor's Sharpe ratio is higher than the original's by +0.51 annualised, with a 95 per cent interval of 0.07 to 0.96, the one difference that is statistically significant at that level when each factor is tested on its own. The two tests differ because the alpha measures what the scaled factor adds to a holding of the original, and the Sharpe ratio difference measures the scaled factor held in the original's place.

**The months after the sample.** None of the twelve Sharpe ratio differences, i.e., the real-time combination against the real-time original and the scaled factor against the original, for each of the six factors, is statistically significant at the 5 per cent level, and for the six volatility-managed factors the intervals are too wide to rule out the differences found on Moreira and Muir's sample. At 136 months the test rejects 2.0 per cent of simulated pairs with equal Sharpe ratios (1.3 to 3.1) where 5 is intended, so these months are weak evidence either way.

**Costs.** A basis point is one hundredth of a percentage point. At 10 basis points per unit of turnover, i.e., per unit of the position traded, the market's alpha is 4.03 per cent a year, statistically significant at the 5 per cent level, and at 20 basis points 3.13, which is not, and the data rule out an alpha above 6.5 per cent a year at that cost.

The expectations were written before the code ran, and the notebooks mark what was added after. French's factors are downloaded at run time and never committed, and the code is public on GitHub<sup id="ref-5"><a href="#note-5">5</a></sup>.

## Terms

- **Realised variance**: the variance of a factor's return within a month, computed from its daily returns.
- **Factor**: the return of a long-short portfolio sorted on a company characteristic, or the market's return above the Treasury bill rate.
- **Sharpe ratio**: the mean return above the Treasury bill rate divided by its standard deviation.
- **Holm's correction**: a rule that sets a stricter threshold for each test when more than one is run together, so that the chance of any false rejection across them stays at or below 5 per cent.
- **Real-time combination**: a mix of the volatility-managed and the original factor whose weights are estimated each month from the months before it.
- **Real-time original**: the original factor alone at its real-time weight.
- **Standard error**: the standard deviation of an estimate.
- **Alpha**: the scaled factor's mean return that the original factor does not explain, from a regression of the one on the other.
- **RMW**: the profitability factor, robust minus weak operating profitability.
- **Basis point**: one hundredth of a percentage point.

## Notes

<ol class="notes">
<li id="note-1">Moreira, A. and Muir, T. (2017). Volatility-managed portfolios. <i>Journal of Finance</i> 72(4), 1611 to 1644. <a href="https://doi.org/10.1111/jofi.12513">https://doi.org/10.1111/jofi.12513</a></li>
<li id="note-2">Cederburg, S., O'Doherty, M. S., Wang, F. and Yan, X. S. (2020). On the performance of volatility-managed portfolios. <i>Journal of Financial Economics</i> 138(1), 95 to 117. <a href="https://doi.org/10.1016/j.jfineco.2020.04.015">https://doi.org/10.1016/j.jfineco.2020.04.015</a></li>
<li id="note-3">Barroso, P. and Santa-Clara, P. (2015). Momentum has its moments. <i>Journal of Financial Economics</i> 116(1), 111 to 120. <a href="https://doi.org/10.1016/j.jfineco.2014.11.010">https://doi.org/10.1016/j.jfineco.2014.11.010</a></li>
<li id="note-4">Ledoit, O. and Wolf, M. (2008). Robust performance hypothesis testing with the Sharpe ratio. <i>Journal of Empirical Finance</i> 15(5), 850 to 859. <a href="https://doi.org/10.1016/j.jempfin.2008.03.002">https://doi.org/10.1016/j.jempfin.2008.03.002</a></li>
<li id="note-5"><a href="https://github.com/ochofer/volatility-managed-portfolios">volatility-managed-portfolios</a>, the repository on GitHub.</li>
</ol>

## Other projects

<div class="pcards">
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Portfolio construction</p>
<p class="pcard__title"><a href="/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a></p>
<p class="pcard__text">Under a long-only index-tracking mandate on French's 49 industries, 1979 to 2026, each of five covariance estimators forecasts less tracking error than its portfolio realises: the realised active return is 22 to 61 per cent more volatile than forecast. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 out-of-sample Sharpe ratios it tests within 0.03 of the published values, 26 of 27 with the value-weighted market counted once.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/note/B-P_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<div class="pcard__body">
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 ownership entities in the US and developed Europe, 302 of them listed companies with a price series, to 5,115 asset holdings, built from Global Energy Monitor's free tracker. Of 19 apparent ownership changes drawn at random and checked by hand, 12 had no corporate event behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/latest/download/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
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
