# Analyzing the successful time of kickstarter projects

## Project objective

The objective of the analysis is to indicate the **time to successful time of kickstarter project** and the **factors that affect the successful of the campaigns the most**.

---

## Dataset overview

The data Kickstarter dataset, originally curated by the Virginia Tech DMKD lab. It can be accessed and downloaded from: https://dmkd.cs.vt.edu/projects/survival/data/18k_Projects.csv (raw project data)

- Number of observations: 4175 campaigns
- Number of variables: 56 features
  - 2 survival core fields: **time to success**, **event**
  - 15 category dummies: art, comics, crafts, dance, design, fashion, film & video, food, game, journalism, music, photography, publishing, technology, theater
  - 6 currency dummies: AUD, CAD, EUR, GPB. NZD, USD
  - 27 campaign- and creator-level features
  - 6 network aggregates
 
**Specifying the starting event**: The time‐zero for every campaign is its **launch date** on Kickstarter, when the project first becomes publicly available for backing.

**Determine the elimination (failure) event**: The “event” is defined as the first day the campaign’s pledged amount meets or exceeds its funding goal. Once that threshold is crossed, the campaign is considered “successful” and exits the risk set.

**Determine the time-to-event variable**: 
*day_succ_i = (the calendar date on which project i first reaches its funding goal) – (the calendar date the project was launched)*

**Determine the censoring variable**: 
Status is set to:
- 1 if the project’s pledged total reached or exceeded the goal on or before day 60
- 0 otherwise (i.e. the project closed without ever hitting the goal). Those with Status = 0 are treated as right-censored at their day_succ value.

---

## Key insights
**Insight from Kaplan Meier estimator**
![](graphs/kp_estimator.png)

**Key factors that affect the result**
