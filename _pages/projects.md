---
layout: archive
title: "Investment research"
permalink: /projects/
author_profile: true
og_image: og-projects.png?v=20261111
og_title: "Investment research"
description: "Research on questions that portfolio managers meet in practice. Each project is specified in writing before it runs, and the code behind every result is public."
---

{% include base_path %}

Each project takes a question that portfolio managers meet in practice and works it through on public data, or on licensed data where the question needs them. It is specified in writing before it runs, and its write-up states the question, the data, the method and the result, including where the result was null, with links to the code so the analysis can be reproduced.

<div class="pcards">
<div class="pcard">
<a class="pcard__img" href="/projects/optimal-vs-naive-diversification/"><img src="/images/thumb-optimal-vs-naive.png" alt="Five covariance estimators under the mandate: each forecast tracking error, hollow, sits to the left of the tracking error it realised, filled" width="240" height="150"></a>
<div class="pcard__body">
<p class="pcard__kicker">Portfolio construction</p>
<p class="pcard__title"><a href="/projects/optimal-vs-naive-diversification/">Optimal versus naive diversification</a></p>
<p class="pcard__text">Under an index-tracking mandate on French's 49 industries, five covariance estimators understate their own tracking error, by 22 to 61 per cent. The replication of DeMiguel, Garlappi and Uppal (2009) reproduces 29 of the 30 Sharpe ratios that carry a band.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/optimal-vs-naive-diversification/dashboard/B-P_dashboard.html" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/optimal-vs-naive-diversification" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<a class="pcard__img" href="/projects/climate-risk-equity-signal/"><img src="/images/thumb-climate-risk.png" alt="Nineteen dots for the ownership changes checked by hand: twelve grey with no transaction behind them, six dark that were real, one hollow that stayed unclear" width="240" height="150"></a>
<div class="pcard__body">
<p class="pcard__kicker">Ownership and prices</p>
<p class="pcard__title"><a href="/projects/climate-risk-equity-signal/">Climate risk as an equity signal</a></p>
<p class="pcard__text">An ownership graph linking 328 listed companies to the 5,115 tracked assets they own. Of 19 apparent ownership changes checked by hand, 12 had no transaction behind them.</p>
<p class="pcard__links"><a class="btn btn--info btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data/releases/download/note-v1.2/what-a-vintage-difference-measures.pdf" target="_blank" rel="noopener"><i class="fas fa-file-pdf" aria-hidden="true"></i> Note (PDF)</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/paper1-hazard-exposure-data" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<a class="pcard__img" href="/projects/volatility-managed-portfolios/"><img src="/images/thumb-volatility-managed-portfolios.png" alt="Monthly realised variance of the market factor, 1926 to 2026" width="240" height="150"></a>
<div class="pcard__body">
<p class="pcard__kicker">Signal evaluation</p>
<p class="pcard__title"><a href="/projects/volatility-managed-portfolios/">Volatility-managed portfolios: a replication, the real-time critique, and the months after the sample</a></p>
<p class="pcard__text">Volatility estimation and position sizing on Ken French's equity factors, backtested out of sample and without look-ahead, replicating Moreira and Muir (2017) and Cederburg, O'Doherty, Wang and Yan (2020). In build: the data and the signal are in place, and nothing in it is a result yet.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/volatility-managed-portfolios" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
<div class="pcard">
<a class="pcard__img" href="/projects/stock-level-tracking/"><img src="/images/thumb-stock-level-tracking.png" alt="Tracking error of the rebuilt universe against CRSP's own return, by year, 1926 to 2024" width="240" height="150"></a>
<div class="pcard__body">
<p class="pcard__kicker">Stock-level index tracking</p>
<p class="pcard__title"><a href="/projects/stock-level-tracking/">A point-in-time benchmark, a long-only mandate, and its performance attribution by sector</a></p>
<p class="pcard__text">A point-in-time S&amp;P 500 universe from CRSP and Compustat, a long-only mandate held close to its cap-weighted benchmark, and an attribution of its active return by sector. In build: the data layer is in place and checked, and nothing of the mandate is a result yet.</p>
<p class="pcard__links"><a class="btn btn--inverse btn--small" href="https://github.com/ochofer/stock-level-tracking" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>
</div>
</div>
</div>
