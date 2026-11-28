---
layout: single
title: "Return prediction: machine learning on the S&P 500's members, corrected for overfitting"
permalink: /projects/ml-return-prediction-backtest-overfitting/
author_profile: true
og_image: og-project-ml-return-prediction-backtest-overfitting.png
description: "Forecasts of each S&P 500 member's return over the next month from twelve characteristics built from CRSP and Compustat, by six models from least squares to a neural network, out of sample from 2006 to 2024. The study follows the method of Gu, Kelly and Xiu (2020), reduced to the index's members, and corrects the best result for overfitting, that is, for having tried many versions and kept the best one. In build: its findings are stated when the study is complete."
---

<p class="pback"><a href="/projects/">&larr; Investment research</a> &middot; Return prediction</p>

<p class="plinks"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/ml-return-prediction-backtest-overfitting" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

This study measures two things on the S&P 500's point-in-time members, i.e., the stocks in CRSP's list of index members on the last trading day of the month before, from January 1991 to December 2024. First, how much machine-learning models add to linear models in forecasting each member's return in the next month, out of sample, i.e., in years on which the model was neither fitted nor chosen. Second, how much of the best result is real once corrected for overfitting, that is, for having tried many versions and kept the best one. The study is in build: it has reached its first milestone, the panel, and its findings on returns are stated when it is complete.

The study follows the method of Gu, Kelly and Xiu (2020)<sup id="ref-1"><a href="#note-1">1</a></sup>, reduced to twelve characteristics and the index's members. A characteristic is a number measured for each member at the end of the month before, such as its market value or its return over the past year. Six models forecast each member's excess return, i.e., its total return in a month less the one-month Treasury bill rate: least squares on three characteristics and on all twelve, the elastic net, a random forest, boosted trees and a neural network with one hidden layer. Each model is fitted with the squared-error loss, i.e., by minimising the sum of its squared forecast errors. For each test year from 2006 to 2024, a model is fitted on the months from January 1991 to six years before it, its configuration, i.e., one choice of its settings such as a penalty or the depth of a tree, is chosen on the five years before the test year, and the chosen fit forecasts the test year.

Each of the 32 configurations of the six models gives one trial: a portfolio long the tenth of each month's members with the highest forecasts and short the tenth with the lowest, held from 2006 to 2024 net of costs. A Sharpe ratio is a portfolio's mean excess return divided by its standard deviation. The overfitting is measured over the 32 trials with two statistics. The deflated Sharpe ratio of Bailey and López de Prado (2014)<sup id="ref-2"><a href="#note-2">2</a></sup> is the confidence, from 0 to 1, that the best trial's Sharpe ratio is above the highest one that 32 trials with no true effect would be expected to show. The probability of backtest overfitting of Bailey, Borwein, López de Prado and Zhu (2017)<sup id="ref-3"><a href="#note-3">3</a></sup> is the share of the ways of splitting the 2006 to 2024 window into two halves in which the trial that is best in one half ranks in the lower half of the other.

**The panel.** The panel is a table with one row per member-month, i.e., one member in one month, holding the twelve characteristics and the excess return. From January 1991 to December 2024 it holds 204,520 member-months. In every one of the 408 months each characteristic is present for at least 92.4 per cent of the members. To check that no characteristic uses data from after the end of the month before, 24 months drawn at random were built a second time from data cut at that date, and they equal the full build in all 144,312 cells.

**The overfitting statistics.** Before either statistic is computed on the study's returns, both are checked on made-up returns with known answers, at the study's own 228 months and 32 trials. With no true effect in any trial, the best trial's deflated Sharpe ratio is above 0.95 in 1 of 4,000 repetitions, where up to 5 per cent would be allowed. The mean probability of backtest overfitting is 0.50 over 1,000 repetitions, the value expected when no trial is better than another. With one trial given a true Sharpe ratio of 1.0 a year, that trial is the best in 98.4 per cent of 1,000 repetitions, the best trial's deflated Sharpe ratio is above 0.95 in 54.2 per cent, and the mean probability of backtest overfitting falls to 0.10.

The levels of the gates and expectations were written into the repository before the code that tests them ran, and the notebooks mark what was added after the results were known. The stock data are CRSP and Compustat, via Wharton Research Data Services, accessed through Queen Mary University of London, from an extraction of 28 September 2026. The market's daily excess return and the one-month bill rate come from Kenneth French's data library<sup id="ref-4"><a href="#note-4">4</a></sup>. The universe and the monthly returns come from the data layer of Stock-level index tracking<sup id="ref-5"><a href="#note-5">5</a></sup>, copied unchanged, and the copy reproduces that study's 440,724 member-months from January 1926 to December 2024. The stock data are licensed, so the repository holds code, tests and aggregates and none of the data. The code is on GitHub<sup id="ref-6"><a href="#note-6">6</a></sup>.

## Terms

- **Point-in-time members**: the stocks in CRSP's list of index members on the last trading day of the month before.
- **Member-month**: one member in one month.
- **Characteristic**: a number measured for each member at the end of the month before, such as its market value or its return over the past year.
- **Excess return**: a member's total return in the month less the one-month Treasury bill rate.
- **Out of sample**: forecast for a year on which the model was neither fitted nor chosen.
- **Configuration**: one choice of a model's settings, such as a penalty or the depth of a tree.
- **Squared-error loss**: fitting a model by minimising the sum of its squared forecast errors.
- **Trial**: the long-short portfolio of one configuration, held from 2006 to 2024 net of costs.
- **Sharpe ratio**: a portfolio's mean excess return divided by its standard deviation.
- **Deflated Sharpe ratio**: the confidence, from 0 to 1, that the best trial's Sharpe ratio is above the highest one that 32 trials with no true effect would be expected to show.
- **Probability of backtest overfitting**: the share of the ways of splitting the 2006 to 2024 window into two halves in which the trial that is best in one half ranks in the lower half of the other.
- **Gate**: a test fixed in advance that the data or the code must pass, which stops the build if it is not met.
- **Expectation**: a test of a result fixed in advance, reported as a finding if it is not met.

## Notes

<ol class="notes">
<li id="note-1">Gu, S., Kelly, B. and Xiu, D. (2020). Empirical asset pricing via machine learning. <i>Review of Financial Studies</i> 33(5), 2223 to 2273. <a href="https://doi.org/10.1093/rfs/hhaa009">https://doi.org/10.1093/rfs/hhaa009</a></li>
<li id="note-2">Bailey, D. H. and López de Prado, M. (2014). The deflated Sharpe ratio: correcting for selection bias, backtest overfitting, and non-normality. <i>Journal of Portfolio Management</i> 40(5), 94 to 107. <a href="https://doi.org/10.3905/jpm.2014.40.5.094">https://doi.org/10.3905/jpm.2014.40.5.094</a></li>
<li id="note-3">Bailey, D. H., Borwein, J., López de Prado, M. and Zhu, Q. J. (2017). The probability of backtest overfitting. <i>Journal of Computational Finance</i> 20(4). <a href="https://doi.org/10.21314/JCF.2016.322">https://doi.org/10.21314/JCF.2016.322</a></li>
<li id="note-4"><a href="https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html">Kenneth French's data library</a>, the daily market excess return and the one-month bill rate.</li>
<li id="note-5"><a href="https://www.carlohofer.com/projects/stock-level-tracking/">Stock-level index tracking</a>, the project page.</li>
<li id="note-6"><a href="https://github.com/ochofer/ml-return-prediction-backtest-overfitting">ml-return-prediction-backtest-overfitting</a>, the repository on GitHub.</li>
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
<p class="pcard__kicker">Asset allocation</p>
<p class="pcard__title"><a href="/projects/rules-based-portfolio/">Rules-based portfolio</a></p>
<p class="pcard__text">Runs a real-money portfolio under rules published before the first order, with every later change dated in the repository: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/guide/guide.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Guide to the dashboard (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
