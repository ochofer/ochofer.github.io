---
layout: single
title: "Stock-level index tracking: a point-in-time benchmark, a long-only mandate, and its performance attribution by sector"
permalink: /projects/stock-level-tracking/
author_profile: true
og_image: og-project-stock-level-tracking.png?v=20261111c
description: "Rebuilds the S&P 500 month by month from CRSP's list of members, at a tracking error of 11.5 basis points a year from 1926 to 2024 against CRSP's own return of the same list, and runs a long-only index-tracking mandate on it from 1999 to 2024, with its active return attributed by sector. The portfolios realise 78.9 to 83.6 basis points a year of tracking error, and each of four covariance estimators forecasts less: the realised active return is 48 to 85 per cent more volatile than forecast. Index changes require 11.4 per cent of the turnover of the portfolio built with Ledoit-Wolf shrinkage."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Stock-level index tracking</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/stock-level-tracking/dashboard/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/stock-level-tracking/note/stock-level-tracking_note_2026-11.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

This study rebuilds the S&P 500 month by month from CRSP's list of members and runs a long-only index-tracking mandate on it from July 1999 to December 2024. The active return is the portfolio's return less the benchmark's, the index it must match, and the tracking error is its standard deviation, as a figure for a year. A covariance estimator, i.e., a method of estimating how the stocks' returns move together, gives the forecast of tracking error, and each of the four tested forecasts less tracking error than its portfolio realises: the realised active return is 48 to 85 per cent more volatile than forecast.

An index fund that holds single stocks follows a benchmark whose members change, whose weights follow market capitalisation, i.e., each company's share price times its shares outstanding, and whose delisted stocks still have a last return. The study has four parts, the *benchmark*, the *tracking error*, the *turnover* and what it is made of, and the *attribution*, i.e., the split of the active return by sector.

**The benchmark.** A basis point is one hundredth of a percentage point. Rebuilt from CRSP's list of index members, month by month from 1926 to 2024 and weighted by market capitalisation, the benchmark tracks CRSP's own return of the same list, weighted the same way, within 11.5 basis points a year. Its momentum and variance spreads, i.e., the return of the top fifth of its members less the bottom fifth, each weighted by market capitalisation, when they are sorted each month on past return or on the variance of their daily returns, have correlations of 0.888 from 1927 and 0.954 from April 1990 with Kenneth R. French's spreads within his largest size quintile.

**The tracking error.** From July 1999 to December 2024 an optimiser holds the long-only portfolio with the smallest forecast tracking error under a mandate: bounds on each stock's and each sector's active weight, i.e., its weight in the portfolio less its weight in the benchmark, a turnover cap, i.e., a limit on the share of the portfolio traded, of 2 per cent a month, Energy and Utilities stocks at no more than half their benchmark weight, two GICS sub-industries, Tobacco and Aerospace and Defense, excluded, and a beta, i.e., the sensitivity of the portfolio's return to the benchmark's, of one. A factor is the return of a long-short portfolio sorted on a company characteristic. Each of the four covariance estimators works on three years of daily returns: the sample covariance and three structured estimators, Ledoit-Wolf shrinkage, a factor model and a principal-component model. A path is one estimator run month by month under the mandate.

The portfolios realise 78.9 to 83.6 basis points a year of tracking error, and every forecast is below the realised figure. On each estimator the bias statistic, i.e., the standard deviation of each month's active return divided by that month's forecast, lies above 1.25 by a margin that is statistically significant at the 5 per cent level on the study's interval, where 1.25 is the upper end of the band, i.e., the range of accurate forecasts fixed in advance. For Ledoit-Wolf the margin is narrow: on a studentised interval at blocks of 24 months, added after the results were known, its lower end is 1.22, so there its excess over 1.25 is not statistically significant.

**The turnover.** Index changes require 2.99 per cent a year of the Ledoit-Wolf path's 26.26 per cent of one-way turnover, i.e., 11.4 per cent of it. Loosening the turnover cap from 0.5 per cent a month to none raises the turnover the optimiser chooses from 6.3 to 59.4 per cent a year on Ledoit-Wolf. The realised tracking error changes by +3.1 basis points a year (−3.6 to +9.8), which is not statistically significant at the 5 per cent level.

**The attribution.** By the method of Brinson and Fachler (1985)<sup id="ref-1"><a href="#note-1">1</a></sup>, each month's active return is split by sector into allocation, i.e., the effect of the sector weights, selection, i.e., the effect of the stocks held within each sector, and interaction, i.e., the sector's active weight times the difference between the portfolio's and the benchmark's return within that sector. In mean absolute monthly terms, sector weights move the active return more than the stocks held within sectors, by a margin that is statistically significant at the 5 per cent level on each of the four paths: allocation averages 16.4 to 16.7 basis points a month in absolute value on the three structured estimators, against 10.6 to 13.8 for selection. Over the 306 months no path's mean active return is statistically significant at the 5 per cent level, which would take about 35 basis points a year, and none of its three sector terms is. The five factors of Fama and French (2015)<sup id="ref-2"><a href="#note-2">2</a></sup> and momentum explain 2 to 13 per cent of the active return's variance.

The levels of the gates and expectations were written before the code that judges them ran, and the notebooks mark what was added after. The stock data are CRSP and Compustat, via Wharton Research Data Services, accessed through Queen Mary University of London, from an extraction of 28 September 2026 and, for the GICS history that gives the sectors, of 10 November 2026. They are licensed, so the repository holds code, tests and aggregate results and none of the data. The code is public on GitHub<sup id="ref-3"><a href="#note-3">3</a></sup>.

## Terms

- **Active return**: the portfolio's return less the benchmark's.
- **Benchmark**: the S&P 500 rebuilt from CRSP's list of members, each stock at its market capitalisation.
- **Tracking error**: the standard deviation of the active return, as a figure for a year.
- **Covariance estimator**: the method that estimates how the stocks' returns move together, from which the forecast tracking error is computed.
- **Market capitalisation**: a company's share price times its shares outstanding.
- **Basis point**: one hundredth of a percentage point.
- **Path**: one covariance estimator run month by month under the mandate.
- **Bias statistic**: the standard deviation of each month's active return divided by that month's forecast, 1 for an accurate forecast and above 1 when the forecast is too low.
- **Allocation, selection and interaction**: the three parts into which the method of Brinson and Fachler (1985) splits the active return by sector.
- **Gate**: a test of the data, at a level fixed before the code ran, that stops the study if it is not met.
- **Standard error**: the standard deviation of an estimate.
- **Studentised interval**: a bootstrap interval built from each resample's distance to the full-sample statistic, divided by that resample's own standard error.

## Notes

<ol class="notes">
<li id="note-1">Brinson, G. P. and Fachler, N. (1985). Measuring non-U.S. equity portfolio performance. <i>Journal of Portfolio Management</i> 11(3), 73 to 76. <a href="https://doi.org/10.3905/jpm.1985.409005">https://doi.org/10.3905/jpm.1985.409005</a></li>
<li id="note-2">Fama, E. F. and French, K. R. (2015). A five-factor asset pricing model. <i>Journal of Financial Economics</i> 116(1), 1 to 22. <a href="https://doi.org/10.1016/j.jfineco.2014.10.010">https://doi.org/10.1016/j.jfineco.2014.10.010</a></li>
<li id="note-3"><a href="https://github.com/ochofer/stock-level-tracking">stock-level-tracking</a>, the repository on GitHub.</li>
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
