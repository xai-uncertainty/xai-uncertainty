---
layout: distill
permalink: /tutorial/
title: Tutorial
description: Tutorial on Aleatoric and Epistemic Uncertainty in Statistics and Machine Learning
nav: true
nav_order: 5

authors:
  - name: Viktor Bengs
    affiliations:
      name: LMU Munich
  - name: Eyke Hullermeier
    affiliations:
      name: LMU Munich
  - name: Willem Waegeman
    affiliations:
      name: Ghent University

bibliography: tutorial-bibliography.bib
---

Without any doubt, the notion of uncertainty is of major importance in machine learning and constitutes a key element of modern machine learning methodology. In recent years, it has gained in importance due to the increasing relevance of machine learning for practical applications, many of which are coming with safety requirements. In this regard, new problems and challenges have been identified by machine learning scholars, many of which call for novel methodological developments. Indeed, while uncertainty has a long tradition in statistics, and many useful concepts for representing and quantifying uncertainty have been developed on the basis of probability theory, recent research has gone beyond traditional approaches and also leverages more general formalisms and uncertainty calculi.

In the statistics literature, two inherently different sources of uncertainty are commonly distinguished, referred to as aleatoric and epistemic [4]. While the former refers to variability due to inherently random effects, the latter is uncertainty caused by a lack of knowledge and hence relates to the epistemic state of an agent. Thus, epistemic uncertainty can in principle be reduced on the basis of additional information, while aleatoric uncertainty is non-reducible. The distinction between different types of uncertainty and their quantification has also been adopted in the recent ML literature [12, 7], and various methods for quantifying aleatoric and epistemic uncertainty have been proposed [5]. In the context of supervised learning, the focus is typically on predictive uncertainty, i.e., the learner’s uncertainty in the outcome y ∈ Y given a query instance x ∈ X for which a prediction is sought. The aleatoric part of this uncertainty is due to the supposedly stochastic nature of the dependence between instances and outcomes, e.g. due to a lack of informative features or noisy class annotations. Therefore, the “ground-truth” is
a conditional probability distribution $$p(\cdot|x)$$ on $$Y$$, i.e., each outcome y has a certain probability $$p(y|x)$$ to occur. Even with full knowledge about the underlying data-generating process, the outcome cannot be predicted with certainty.
Obviously, the learner does not have full knowledge of $$p(\cdot|x)$$. Instead, it produces a “guess” $$p(\cdot|x)$$ on the basis of the sample data provided for training. Broadly speaking, epistemic uncertainty is uncertainty about the true probability and hence the discrepancy between $p$ and \hat{p}. This (second-order) uncertainty can be captured and represented in different ways. One approach is to train a probabilistic predictor in a more or less standard way, and to quantify the uncertainty of that predictor in a kind of post hoc manner. An example is the estimation of epistemic uncertainty in terms of the mutual information between the target variable and the model parameters [3, 2, 15].

Another idea is to estimate uncertainty in a more direct way, and to let the learner itself predict, not only the target variable, but also its own uncertainty about the prediction <d-cite key=charpentier2020posterior></d-cite> 
For example, instead of predicting a probability distribution $$p(· | x)$$, the learner may predict a second-order distribution (distribution of distributions) or a set of distributions [14]. Its epistemic uncertainty is then represented by the “peakedness” of the former or the size of the latter.
