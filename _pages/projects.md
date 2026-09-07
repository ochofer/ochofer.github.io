---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
og_image: og-projects.png
og_title: "Quantitative investment projects: public data, public code"
description: "An ownership graph linking 4,900 physical assets to 302 listed companies, public with its code. The return test it was built for was set aside on power, before it ran."
---

{% include base_path %}

Alongside my other academic research, I also work on quantitative questions in financial markets. These are self-directed research exercises using public data. Each write-up states the question, the data, the method, and the result, including where the result was null, and links to the code so the analysis can be reproduced.

## In progress

**Climate risk as an equity signal.** Companies own physical things. Power stations, pipelines, mines, cement works. Those things sit in places, and places have weather. The question was whether investors price the risk that weather damages those assets or interrupts what they produce.

The hard part was never the question, it was the join. Which company owns which asset, and what that company's shares did, are recorded in different places under different identifiers, and neither contains the other. So most of the work went into building that bridge and then trying to prove it wrong. The ownership graph is built from Global Energy Monitor's free tracker. 328 ownership entities resolve to the US and developed-Europe listed universe, 302 of them priceable, covering 4,900 of the 5,115 tracked assets.

**The return test was set aside before it ran.** The design was written down and fixed first. Then a power calculation showed it could not detect an effect of the size this literature reports, on the history available. Running it anyway would have produced a null that meant nothing. That is worse than no test, because a null reads like a finding to anyone who does not check how much power stood behind it. The calculation is in the repository, so the decision can be audited rather than taken on trust.

**What goes up first is a data-quality note.** The tracker publishes its database in releases, and the releases do not agree with each other. What an asset is recorded as, and who is recorded as owning it, changes from one to the next. Anyone building a history from a single current snapshot inherits those changes without seeing them. That is a measurement problem before it is a finance problem, and it is what this data layer turns out to be good for. The note goes up here with its code when it is done, and no number from it appears before then.

The data-acquisition layer is public and deliberately independent of any test: [github.com/ochofer/paper1-hazard-exposure-data](https://github.com/ochofer/paper1-hazard-exposure-data){: target="_blank"}. It was built to be reusable by whatever the analysis turned out to be, which is why setting the return test aside required no change to it at all.

Each project publishes its code in a public repository as its write-up goes up, so the analysis can be run rather than taken on trust.

For written analysis aimed at decision-makers rather than academic readers, see the two DEMETRA policy briefs under [Publications](/publications/).
