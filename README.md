# Control Charts for Multinomial Data

A literature review examining statistical process control (SPC) methods for monitoring processes with **multinomial (multi-category) data** — i.e. situations where items are classified into more than two categories rather than simple conforming/nonconforming outcomes. Completed as the first project for the *Statistical Quality Control* course, MSc in Statistics, Athens University of Economics and Business (AUEB).

## Repository Contents

| File | Description |
|---|---|
| `Control_Chart_For_Multinomial_Data.pdf` | Full report reviewing traditional and advanced control charts for multinomial/multi-attribute quality data. |

## Report Overview

The report starts from the fundamentals of control chart design (center line, control limits, Type I error, chance vs. assignable causes) and traditional attribute charts (p, np, c, u charts), then explains why these univariate charts fall short when a process outcome can fall into **more than two categories**. It then reviews several methods developed specifically for multinomial processes:

- **Pearson's Chi-Square Control Charts** — monitor deviations from expected category proportions using a goodness-of-fit statistic.
- **MACC and LR-MACC** (Multiattribute / Likelihood Ratio-based Multiattribute Control Charts) — simultaneously monitor multiple correlated quality attributes.
- **CUSUM Control Charts** — cumulative sum charts for individual observations (n = 1), effective at detecting small and gradual shifts.
- **GLR Control Charts (MGLR)** — Generalized Likelihood Ratio charts that estimate the size and direction of an unknown shift.
- **Fuzzy Multinomial Control Charts (FM-charts)** — handle cases where classification into categories is vague or overlapping, using fuzzy set theory and membership functions.
- **Multivariate Attribute Control Charts using Mahalanobis Distance** — monitor proportions across all defect categories jointly, avoiding the inflated Type I error of running separate p-charts per category.

## Key Takeaways

- Traditional p and c charts are univariate and cannot capture correlated, multi-category quality patterns.
- CUSUM and GLR-type charts outperform basic Shewhart charts for detecting small or unknown-direction shifts, at the cost of added computational complexity.
- Fuzzy multinomial charts are best suited to cases where classification boundaries between categories are not sharp.
- Mahalanobis-distance-based charts test proportions across all categories jointly, improving sensitivity to overall shifts in the defect distribution.
- Promising future directions include combining fuzzy logic with machine learning, and using ML/neural network methods for real-time control limit adjustment and automated root-cause diagnosis.

## References

Full citation list is included at the end of the report (Nelson 1987; Marcucci 1985; Montgomery; Mukhopadhyay 2008; Psarakis & Topalidou 2009; Ryan, Wells & Woodall 2011; Taleb & Limam 2005; Lee et al. 2017; Amirzadeh, Mashinchi & Yaghoobi 2008; and others).

## Author

Konstantinos Grammenos — MSc in Statistics, AUEB
Supervisor: Prof. S. Psarakis
