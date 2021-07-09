---
layout: post
title: 'One Paper A Day: Reviewing dataset paper "A Dataset for Multilingual Epidemiological Event Extraction"'
---

### Preface
*This is the first article in the series of One Paper A Day. In this series, I will commit to reviewing and summarising one article every day. Papers reviewed likely to fall under the category of machine learning, software engineering or medicine.*

## TLDR
This paper essentially provides a corpus for development of NLP tools and techniques for processing text related to Emerging Infectious Diseases (EID). Paper can be found [here](https://aclanthology.org/2020.lrec-1.509.pdf). 

## Why should you be interested in this paper?
- Suitable for people developing NLP tools for surveillance of EID.
- There are few other EID corpuses available on the web.
- As paper was published in 2020, it has a fairly recent publication (relative to this blogpost) with a comprehensive literature review of both NLP techniques and corpus. 

## Key learning points

### Literature review
- Event extraction methods applied on EID news sources can be divided into three types:
    - Pattern based: Rules and template to extract events from text through representation and explotation of expert knowledge
    - Data driven: Statistical techniques to discover the relations in text
    - Hybrid of pattern based and data driven approaches
- Review of existing event extraction methods published:
    - [DANIEL](https://daniel.greyc.fr/public/index.php?a=AboutDAnIEL)
    - [BIOCASTER](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2639299/)
    - [PULS](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6587687/)
    - [GRITS](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5028852/)
- NLP applied on internet search data to look for specific EID trends e.g. Influenza
    - Sources of internet search data: Google, Twitter, Yahoo

### Methods
- Corpus creation: 
    - Data extracted from online Promed articles from 1 Aug 2013 to 31 Aug 2018
    - Data cleaning done to remove boilerplate content in each of the articles
    - Data filtering to extract languages of interest
    - K means clustering applied on articles 
    - Deduplication of data was done to remove potential duplicates. Tool used is ONION.
    - Control dataset created with Huffpost news articles from 2012 to 2018
- Corpus statistics:
    - Training set comprises of 10,000 English articles and 2,996 French articles
    - Human annotated datasets, consisting of 444 English articles and 2,722 French articles, provided the ground truth to evaluate models developed.
- DANIEL for extraction:
    - Segmentation
    - Event detection
    - Event localisation
    - Output is disease location pair
- Text classification model:
    - Supervised classification methods evaluated: naive bayes, random forest, neural network
- Performance metrics considered:
    - Recall and precision conisdered for evaluation of DANIEL
    - Recall, precision, F measure metrics for evaluation of text classification models

### Results
- DANIEL: 
    - F score of 75%, precision of 60% for English articles
    - Precision of 74%, recall of 83% for French articles
- Text classification model (English)
    - Highest precision of 80% by Random Forest
    - Highest recall of 76% by Neural Network
    - Highest F measure of 74% by Random Forest
- Text classification model (English)
    - Highest precision of 80% by Random Forest
    - Highest recall of 74% by Naive Bayes
    - Highest F measure of 67% by Random Forest

# Key contributions
- Large multilingual EID dataset available [here](https://zenodo.org/record/3709617#.YOfWcXUzZH4)
- Baseline performance of NLP techniques for event extraction and text classification methods
