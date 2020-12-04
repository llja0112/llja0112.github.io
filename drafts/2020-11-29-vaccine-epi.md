---
layout: post
title: "Simulations to calculate effects of epidemiological interventions"
---

# Objectives
- To estimate the trend and/or course of the disease
> Number of people affected
> Outbreaks and how they might be controlled with vaccines
- Look at various policies' and vaccines' effectiveness in controlling disease and achieving the goal of reopening the economy

# Methodology
- Acquisition of data from official open source data
- Model data's chronological trend through statistical methods
> Normal distribution
> Time series methods
> Categorise by country

- Estimate how various interventions affect the trends
> PGM
> Gaussian processes
> if, else probabilities
> possibilities should include plausible public policies and new therapeutics like vaccines

- Metrics of comparison
> Differences in trend
> Potential benefit in keeping certain segments of the population healthy

- Estimate the trend of COVID infection
> Model infectious trends before intervention and after the intervention
> Intervention can be defined by either vaccines or policies

- Efficacy of vaccines (Comparing the proportions of infected patients in phase 3 of clinical trial)

# Current state of the art
Transmissibility also known as basic reproduction number, R0. It is calculated by equation (1), where Beta is the number of infection producing contacts per unit time and Tau is the mean infectious period.

R0 = Beta multiply by Tau - (1)

The esimation of R0 is calculated with the by the equation (2) where N(t) is the number of diagnosed infections over time period defined by t.

K = d ln(N(t)) / d t - (2)

# Alternative way to caclculating R0

We can offer a more in depth calculation of R0 by taking into consideration the different factors affecting infectivity:
- Infectivity of asymptomatic patients differ from symptomatic patients
- Different types of contacts that index patient has
> Contacts who they see on a daily basis (e.g. family who lives together with patient)
> Contacts who they see in a one off encounter (e.g. the fellow commuter on the train, bus, car)
> Where contacts are defined as people who have sufficient contact time with index patient to enable infectivity
- The number of contacts generated can be estimated with a recursive algorithm

# Calculating the probability of imported cases based on countries

Probability(imported case | country) = number of new infected cases D0 / population number - number of confirmed infected cases D-1 

# Comparing vaccine efficacy

Comparing characteristics of each vaccine
- Trial phase
- Population characteristics for each of the trial
- Efficacy

Comparison between current methods against previous known vaccines
- Any shortcuts used for the vaccines at the current moment?
- What allowed the acceleration of vaccine development?
- Implications on the clinical setting.

