---
layout: post
title: On Reproduction Number (R0) and Singapore's real time R0
---

## Introduction

Within a few weeks, we will be reaching the 1 year mark of the SARS-CoV2 pandemic outbreak in Singapore. [Our first case was detected on the 23rd January 2020.](https://www.channelnewsasia.com/news/singapore/singapore-covid-19-outbreak-evolved-coronavirus-deaths-timeline-12639444)

As I am writing this post, [we are going into phase 3 of our cicuit breaker measures, on the 28th of December 2020.](https://www.gov.sg/article/moving-into-phase-3-of-re-opening-on-28-dec-2020). I thought it would be meaninful, at this critical juncture, to use publicly available data to perform an objective assessment of the current SARS-CoV2 pandemic situation in Singapore. Of note, from the public health standpoint, regular objective assessments of an infectious disease outbreak is often necessary to determine public policy measures (e.g. social distancing, number of visitors allowed to a home, number of diners allowed to sit together at a dining table, etc.).

Robust metrics of transmission based on well established models are often used to make these assessments. The most common, basic and well understood metric is the number of new cases of an infectious disease reported daily. In Singapore, this metric is reported over [social media](https://www.facebook.com/sghealthministry), [mainstream media](https://www.straitstimes.com/) and [government official websites](https://www.moh.gov.sg/covid-19) regularly. Other metrics not commonly discussed on these media platforms are:

1. Reproduction Number (R0)
2. Attack rate
3. Infection rate
4. Serial Interval
5. Transmission risk and rate

For this particular blog post, I would like to discuss R0. This metric received significant attention and discussion, after a popular Facebook post by Singapore Prime Minister’s wife Mdm Ho Ching as linked [here](https://www.facebook.com/permalink.php?story_fbid=1604709026383592&id=100005335308340). I present a quote from her Facebook post:

> In addition, we have Covid safe precautions in place among our people, like safe distancing, mask wearing, hand sanitising or cleaning, and crowd management.  This is critical in driving down average secondary transmission from an R0 of 2-3, down to an R0 of about 1. This means instead of infecting on average 2-3 other persons, an infectious C+ index case in Singapore infects about 1 other person. <br> **Ho Ching**

## What is the reproduction number, R0?

R0 can be defined as the number of secondary infections produced from an actively infective person. There are numerous great videos on YouTube explaining this concept here and here. Wikipedia also has a great explanation of R0 [here](https://en.wikipedia.org/wiki/Basic_reproduction_number).

R0 can be calculated in many ways. The basic formula looks deceivingly simple: Average number of infection producing contacts per unit time (Beta) multiplied by the mean infectious time period (Tau) as shown in equation (1) below.

Equation here - ()

However, there are many difficulties involved in deriving both of these variables necessary for the calculations:
- In the early days of any pandemic, there will be limted data to help us accurately derive both of these variables. This can lead to inappropriate public health measures, espeacially when we underestimate the severity of an outbreak.
- These variables are also affected by public health measures such as movement control, quarantines, lockdowns, social distancing, mandatory orders to wear masks, etc. As more measures are instituted, we can further limit the mean infectious time period of infected individuals thus effectively limiting the spread.
- As interventions/treatments such as vaccines and antivirals appear, the number of infection producing contacts per unit time can be reduced.
- Lastly, the task of producing data to update these numbers are unusually onerous and difficult to undertake. For instance, to calculate just the number of infection producing contacts require (1) Aggressive contact tracing (2) Detailed history taking and physical examination of contacts. Most of the time, this is reduced to questionnaires. (3) Clinical investigation of close contacts. In the context of SARS-CoV2, a nasapharyngeal PCR and blood serological testing would be minimally indicated.

## Estimations of Singapore's R0 value

### Data

I extracted data on the daily number of new SARS-CoV2 infections between 1st of January 2020 to 20th of December from Singapore's Ministry of Health website, specifically from it's [situation report webpage](https://covidsitrep.moh.gov.sg/). The report is presented on a sleek graphical interface powered by [Plotly](https://plotly.com/). For this study, I extracted the daily number of new cases reported under 3 subcategories: overall, community and dormitory infections. The CSV of the data can be found here.

### Methodology

To estimate the R0 value, I used the modelling technique from *Abbott et al.*'s R package [EpiNow](https://github.com/epiforecasts/EpiNow). This was built upon the modelling techniques found in *Anne Cori et al.*'s R package [EpiEstim](https://github.com/mrc-ide/EpiEstim). There are several factors considered as part of this modelling approach, such as the generation time, incubation period and reporting delay. If we refer to the simplistic illustration of calculating R0 in (1), the generation time and incubation period are analogous (but not directly equivalent) to the beta and tau variables respectively. To ensure realistic estimates of R0, we have to factor in the uncertainty between the time point of infection and the time point of reporting a new case. A generative Bayesian model is established. Subsequently, Markov Chain Monte Carlo methods are used to estimate the posterior distribution and derive the R0 value. I have to admit that there is a lot of handwaving in my description of the algorithm. To keep this post short, I will leave a more detailed description on the approach for a seperate blog post. For reproducibility of my results, the corresponding R code with the parameters used for the modelling and the analysis can be found in my repository here.

### Results

The analysis was performed on a daily basis between 1st January 2020 to 20th December 2020 for the 3 subcategories of data I extracted: overall, community and dormitory. The model produces 3 estimates: (A) Cases by date of report. (B) Cases by date of infection (C) R0.

The first figure here shows the results for overall infections:

![Singapore overall R estimates]({{site.url}}/assets/Reproduction_overall.png)
*Singapore's overall R0 estimates*

The second figure here shows the results for community infections:

![Singapore community R estimates]({{site.url}}/assets/Reproduction_community.png)
*Singapore's community R estimates*

The third figure here shows the results for dormitory infections:

![Singapore dormitory R estimates]({{site.url}}/assets/Reproduction_dormitory.png)
*Singapore's dormitory R estimates*

We also estimate the latest effective reproduction number, rate of growth and doubling/halving time:

~ | **Overall** | **Community** | **Dormitory**
Effective reproduction number | 1.4 | 0.5 | 0.91
Rate of growth | 0.11 | -0.15 | -0.024
Doubling/halving days | 6.5 | -4.6 | -29

## Discussion

## Disclaimer
