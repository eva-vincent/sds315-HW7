# Causal Inference & Statistical Resampling
## Project Overview
This repository contains two statistical analyses using R to address challenges in observational data. The projects focus on constructing confidence intervals for biological traits and applying propensity score matching to estimate causal effects in political campaigning.

## Key Analyses
### 1. Biological Trait Analysis (Arm Crossing)
Objective: Determine if there is a statistically significant difference in arm-crossing preference (Left-over-Right vs. Right-over-Left) between sexes.

Methodology:

Calculated sample proportions and standard errors.

Constructed 95% Confidence Intervals using both theoretical formulas (Central Limit Theorem) and bootstrapping.

Result: The analysis found a 95% confidence interval of [-0.093, 0.190] for the difference in proportions. Since the interval includes 0, we fail to reject the null hypothesis; there is no statistically significant difference in arm-crossing preference between sexes.

### 2. GOTV Campaign Effectiveness (Causal Inference)
Objective: Isolate the true causal effect of "Get Out The Vote" (GOTV) phone calls on voter turnout in the 1998 election, adjusting for confounding variables.

Challenge: Initial analysis suggested a massive 20% increase in turnout among those called. However, exploratory data analysis revealed significant confounders: older people and past voters were both more likely to be called and more likely to vote regardless of the call.

Methodology (Matching):

Used the MatchIt library to perform covariate matching.

Matched treated individuals (called) with control individuals (not called) who shared similar ages, party affiliations, and voting histories to create a balanced dataset.

Result: After controlling for confounders, the estimated effect of the phone call dropped but remained significant. The matched analysis showed that GOTV calls increased voter probability by approximately 7.9% (CI: 1.0% to 14.7%), providing a more accurate causal estimate than the naive comparison.

## Tech Stack
Language: R

Libraries: tidyverse, MatchIt (for causal inference), mosaic, ggplot2

Techniques: A/B Testing, Bootstrapping, Confounder Identification, Covariate Matching
