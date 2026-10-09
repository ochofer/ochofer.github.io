---
layout: single
title: "Rules-based portfolio"
permalink: /projects/rules-based-portfolio/
author_profile: true
og_image: og-project-rules-based-portfolio.png
description: "A real-money portfolio at 70/30, global equity and euro government bonds, run under rules fixed before the first order. The split is the largest equity weight whose worst fall from 1999 to 2025 stayed within 35 per cent."
---

<p class="pback"><a href="/projects/">&larr; All projects</a> &middot; Asset allocation</p>

<p class="plinks"><a class="btn btn--info btn--small" href="https://www.carlohofer.com/rules-based-portfolio/" target="_blank" rel="noopener"><i class="fas fa-chart-line" aria-hidden="true"></i> Dashboard</a> <a class="btn btn--inverse btn--small" href="https://github.com/ochofer/rules-based-portfolio" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> Code on GitHub</a></p>

I run a real-money portfolio under written rules: 70 per cent in a global equity ETF and 30 per cent in a euro government bond ETF. The mandate's risk limit, a worst fall of about one third, sets the split: on monthly euro returns from 1999 to 2025, 70 per cent is the largest equity weight whose worst fall stayed within 35 per cent (34.7 per cent, from August 2000 to March 2003). On each monthly cycle day the top-up buys the sleeve furthest below its target weight, and if the equity weight is outside the band from 65 to 75 per cent the portfolio is brought back to 70/30. The rules were fixed and tagged on 7 October 2026, before the first purchases the next day. A program computes the record from the private ledger, and a dashboard draws it: the orders and their costs, the drift of the weights, the rebalancing the rules produce, the look-through of both ETFs and the factor exposures of the equity ETF.

The mandate, the test and the rules are in the repository on GitHub. The dashboard is rebuilt every Monday and on each cycle day.
