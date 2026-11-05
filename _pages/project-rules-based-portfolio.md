---
layout: single
title: "Rules-based portfolio"
permalink: /projects/rules-based-portfolio/
author_profile: true
og_image: og-project-rules-based-portfolio.png?v=20261105
description: "Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks."
---

<p class="pback"><a href="/projects/">&larr; All projects</a> &middot; Asset allocation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

Runs a small real-money portfolio under rules published before the first order: two UCITS ETFs at 70/30, a monthly cycle with pre-trade checks, look-through exposure and ex-ante risk on a public dashboard.

The portfolio holds a global equity ETF and a euro government bond ETF. The mandate, the ten rules and the choice of the two funds were written and tagged on 7 October 2026, before the first purchase on 8 October. On the fifth of each month a program checks the rules against the positions, proposes the orders the rules call for and writes a report before any order is placed. Every departure from the rules is kept in a register. A monthly note follows each cycle day, and a quarterly report follows each quarter, the first in January 2027.

The split is set by the risk limit. The mandate asks for the highest long-run growth over five to ten years within a worst fall of about one third. On monthly euro returns from February 1999 to December 2025, built from Kenneth French's market returns and ECB series, 70 per cent equity is the largest target weight whose worst fall under the band rule stayed within 35 per cent: 34.7 per cent from August 2000 to March 2003. The test runs on index history and says nothing about the record itself. Anyone can rerun it from the repository.

The dashboard, rebuilt every Monday and on each cycle day, draws every figure from a committed table: the weights and the drift, the costs by source, the look-through to the countries, sectors, currencies and issuers inside both funds, the equity fund's factor loadings, and an estimate of the portfolio's volatility and one-month value at risk on index returns at the look-through weights. Two reference portfolios computed from the same contributions without costs show the implementation cost. No return is offered as evidence for the rules: with a book this size and a record of a few years, a return cannot show whether the rules are good.
