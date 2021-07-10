---
layout: post
title: 'One Paper A Day: Reviewing EID NLP paper "Evaluation and Verification of the Global Rapid Identification of Threats System for Infectious Diseases in Textual Data Sources"'
---

## TLDR
This paper proposes a new NLP based EID system known as The Global Rapid Identification of Threats System (GRITS).

## Why should you be interested in this paper?
GRITS is one of the few NLP based EID systems known in the literature. It was developed by EcoHealth Alliance to identyify EID in digital textual sources of data. Other systems include [DANIEL](https://daniel.greyc.fr/public/index.php?a=AboutDAnIEL), [BIOCASTER](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2639299/) and [PULS](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6587687/).

## Key learning points

### Limitations of traditional biosurveillance systems
- Limited geographic coverage
- Poor quality of underlying healthcare infrastructure in certain parts of the world
- Lack of laboratory capacity
- Reticent governments in annoucement of EID in view of possible economic and reputation harm
- Furthermore, traditional systems are designed to detect known infectious disease threats (e.g. Influenza, Ebola, etc.)
- Other complementary systems to traditional systems: Syndromic disease surveillance, digital biosurveillance

### Method
- Data: 150,000 articles collected over 2-3 year periods. Analysts manually assigns labels for diseases. Subset of 12,000 articles used for training. 3,500 articles used for testing.
- Search function: Indexed with Elasticsearch. Elasticsearch also assigns relevance scores to individual terms using TDIF. Additionally, extracted feature metadata for each articles are used to sort search results.
- Feature extraction: Disease related and contextual features are extracted from texts. Features are stored as annotations on the text. They are also further categorised as disease, pathogens, symptoms, hosts and modes of transmission. 
    - Python's standard pattern-mathcing libraries and NLTK package used to match keywords from a variety of compiled ontologies of terms related to infectious disease and public health
        - Biocaster ontology
        - GRITS ontology
        - HealthMap disease labels
        - The disease ontology
        - USGS topographic feature vocab
        - Wordnet
    - Dates are extracted from Stanford SUTime Java library
    - Case counts identified using the CLiPS Pattern library's search module
- Classsifier training, verfication and evaluation
    - Inputs is a vector of features extracted by GRITS' NLP algorithms.
    - SKLearn's logistic regression used, in conjunction with multiclass one vs rest classifier, to train model for prediction of the disease referred to by the text.

### Results
- Precision 64%, recall 63% and F1 score 0.317. Presumably, this is the average precision, recall and F1 scores of model predictions of all diseases tested by the researchers. Detailed performance of individual disease predictions were published in the original article.

## Thoughts
- No comparison was made with other classifiers. Mostly a descriptive paper about a new EID surveillance system powered by NLP.
- Unclear description of how data was obtained. Presumably the data was extracted from Healthmap.
- Otherwise, it is a succinct explanation of the essential methods to develop a similar system.
- I also agree that the system is useful for public health specialists and epidemiologists. It can complement existing surveillance systems to improve accuracy and promptness of reporting new EID and instituting relevant public health actions.
