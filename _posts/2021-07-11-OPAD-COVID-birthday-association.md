---
layout: post
title: 'One Paper A Day: Reviewing public health paper "Assessing the Association Between Social Gatherings and COVID-19 Risk Using Birthdays"'
---

## TLDR
This paper describes the association between social gatherings (e.g. Birthdays) and COVID-19 infections. Paper can be found [here](https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2781306)

## Why should you be interested in this paper?
- Studying the impact of various types of social contact and its relation to COVID-19 infections was considered a challenging task by the authors for 2 reasons:
    - Large dataset required
    - Problems of confounding
- This paper overcomes these problems by using patients' birth dates as a surrogate marker of a social contact

## Key Learning points

### Data sources
- Household birthdays and household COVID-19 infections between 1st January 2020 and 8th November 2020 from a large commercial private insurance database was used.
- The data contains linkages for all household members enrolled on a single insurance plan.

### Methods
- Statistical analysis: 
    - Hypothesis made that COVID infections would happen within a 2 week period after birthday. Falsification analysis made by studying the correlation of infections 4-8 weeks prior to birthday.
    - Assumption made that the likelihood of COVID-19 infection is associated with:
        - social distancing behaviour of household members
        - COVID-19 prevelance among social groups in which any type of social gathering occurs
        - Adjustments to the correlation between birthdays and COVID-19 infections made according to the stage of pandemic. Prevelance of infections varies according to stage of pandemic e.g. early stages have lower prevelance. Later stages have higher prevelance.
    - Multivariable linear model of COVID-19 diagnosis in a household in a given week as a function of birthday occuring in the household 2 weeks prior, county and week fixed effects, family level covariates. 
- Subgroup analysis:
    - Adult birthday vs child birthday
    - Milestone birthday events, e.g. 40yo vs 50yo vs 60yo birthday celebrations
    - Voters attending mass rallies
    - Counties with different social distancing guidelines
- Sensitivity analysis:
    - Analysis conducted to address concerns that birthdays might disproportionately happen on later stages of the pandemic where prevelance is high. This would lead to a spurious conclusion where infections were driven by other risk factors rather than a social gathering to celebrate a birthday. This was effectively mitigated by performing analysis by calender quarter and demographics (e.g. US census region, household size, share of households with any children, industry of household's primary insurance subscriber, etc.).
    - Possibility of infections 4-8 weeks before household birthday analysed. Finding correlation between infections during this period with birthdays within the household would suggest that main hypothesis is not correct.

### Results
- 36.4 per 10,000 individuals had birthdays 2 weeks prior to their COVID-19 diagnosis. Within the fifth decile of population by COVID infections, 28.7 per 10,000 individuals had COVID-19 diagnosis. At baseline, 27.8 per 10,000 individuals had COVID-19 diagnosis.
- Essentially, individuals had a 31% relative increase in likelihood of household COVID-19 infections when an individual within the household had a birthday 2 weeks prior.
- Other factors did not affect this correlation found: political inclincations, precipitation in the county, county level shelter in place policies, etc.
- Other noteworthy point is that children birthdays present a higher risk of COVID-19 infection, as compared with adult birthdays.

### Thoughts
- Results are unsurprising given the nature of birthdays. Attendees are likely not wearing masks during consumption of meals, singing birthday songs, etc. In addition, the contact time is likely to be prolonged, minimally an hour of celebration.
- The idea of studying the impact of social gatherings through birthdays from an insurance database is novel and refreshing.
- However, the limitations are clear. Social gatherings take many forms e.g. marriage anniversaries, baby showers, funerals, weddings, etc. It is unlikely that a birthday celebration is a good approximation of the kind of contact and infective transmissibility these other social gatherings entail.
- Finally, a Singapore study in Lancet published [here](https://www.thelancet.com/article/S1473-3099(20)30833-1/fulltext) gave a more detailed breakdown of the risk associated with each kind of social gathering. This was accompanied with COVD-19 seroprevelance data in the studied population, which provides a more robust epidemiological understanding of COVID-19 transmissions/transmissibility.
