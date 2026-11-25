Standard laryngoscopy is better than the video-assisted variant
================
Tristan Tangdiongga
2026-10-25

## Introduction

In this document, multivariate regression will be applied to a dataset
of an randomized controlled trial (RCT) about laryngoscopy for
preoperative intubation.

## Prerequisites

The packages `tidyverse` and `gtsummary` were used for the data
manipulation and statistics, respectively. The dataset that was used is
the `laryngoscope` dataset from the `medicaldata` library.

``` r
library(tidyverse)
library(gtsummary)
library(medicaldata)

lar <- laryngoscope
```

## Descriptive statistics

The descriptive statistics are displayed in table 1. A total of 99
people were randomized between 2 groups. Standard laryngoscopy (Standard
Macintosh 4) was compared to video-assisted (AWS Pentaz Video) for
preoperative intubation. No significant differences were reported
between the 2 groups.

The table was made with the `tbl_summary()` function of the `gtsummary`
package.

| **Characteristic** | **Standard** (N = 49) | **Video-assisted** (N = 50) | **p-value** |
|:---|:--:|:--:|:--:|
| Age | 49 (44, 53) | 50 (47, 54) | 0.6 |
| Gender |  |  | 0.8 |
| Female | 39 (80%) | 39 (78%) |  |
| Male | 10 (20%) | 11 (22%) |  |
| ASA |  |  | 0.14 |
| 2 | 7 (14%) | 15 (30%) |  |
| 3 | 40 (82%) | 32 (64%) |  |
| 4 | 2 (4.1%) | 3 (6.0%) |  |
| BMI | 42.5 (41, 44) | 41.4 (40, 43) | 0.2 |
| Mallampati |  |  | 0.059 |
| 1 | 14 (29%) | 21 (42%) |  |
| 2 | 21 (44%) | 18 (36%) |  |
| 3 | 13 (27%) | 7 (14%) |  |
| 4 | 0 (0%) | 4 (8.0%) |  |

Demographics characteristics by randomized group

## Multivariate regression

The outcomes of the trial were analyzed with multivariate regression in
table 2, either linear or logistic, while adjusting for the
demographics.

The multivariate regression analysis was done with the `lm()` or `glm()`
function from the `gtsummary` package for linear and logistic
regression, respectively.

| **Characteristic** | **Standard** (N = 49) | **Video-assisted** (N = 50) | **p-value** |
|:---|:--:|:--:|:--:|
| Time (sec) | 30 (25, 35) | 45 (39, 51) | \<0.001 |
| 1st attempt | 26 (23, 29) | 41 (36, 46) | \<0.001 |
| Successful | 49 (100%) | 46 (92%) | \>0.9 |
| 1st attempt | 45 (92%) | 43 (86%) | 0.5 |
| Bleeding | 0 (0%) | 2 (4.0%) |  |
| Difficulty (0-100) | 38 (30, 46) | 52 (43, 61) | 0.033 |
| Sore throat |  |  | 0.5 |
| None | 32 (67%) | 34 (68%) |  |
| Mild | 12 (25%) | 9 (18%) |  |
| Moderate | 3 (6.3%) | 5 (10%) |  |
| Severe | 1 (2.1%) | 2 (4.0%) |  |
| Good glottic view | 38 (78%) | 43 (86%) | 0.2 |

Outcomes by randomized group

## Conclusion

Standard laryngoscopy is a faster (p \< 0.001) and easier (p = 0.033)
way to achieve intubation than video-assisted laryngoscopy.
