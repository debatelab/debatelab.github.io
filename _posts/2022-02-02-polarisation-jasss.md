---
layout: post
title: "Arguments Drive Polarisation Dynamics in a Formal Model"
author: "Felix Kopecky"
categories: journal
tags: [polarization, argumentation, opinion dynamics]
---

[📝 [Paper](https://doi.org/10.18564/jasss.4767)] 
[📓 [Jupyter notebooks](https://zenodo.org/record/5523209)]
[🐍 [Python library](https://pypi.org/project/taupy/)]

Argumentation (the process of producing arguments and responding to those put forward by others) can influence opinion dynamics in artificial agents: from [previous research](https://link.springer.com/book/10.1007/978-94-007-4599-5) we already know that argumentation can be conducive to agreement among artificial agents, and that the effect size depends on types of argumentative behaviour.

If argumentation can bring about agreement in debates, does it then also drive polarisation or de-polarisation? As a technical concept, polarisation can be understood as a characterisation of disagreement. Sometimes agents agree on many shared background beliefs, but disagree on how exactly to apply them in a specific scenario. Such disagreements need not result in substantial population fracturing. But agents can also cluster into distinctive groups with high internal agreement and high disagreement to other groups. Disagreements that cluster in such a way are polarised in the sense of *belief*, or  *issue polarisation*. 

## A model of argument introduction and response

The paper “[Arguments as Drivers of Issue Polarisation in Debates Among Artificial Agents](https://doi.org/10.18564/jasss.4767)” looks into the polarisation dynamics in a formal debate model built on the theory of dialectical structures. In the model, agents participate in the debate through (1) introductions and (2) responses:

 1. They purposefully introduce arguments following one of five strategies. These strategies govern how the agents select premises and conclusions from the pool of sentences under discussion. 

 2. They respond to the introductions from other agents by adapting their belief system to satisfy the logical constraints from these newly introduced arguments.

## Results show the influence of argumentation on polarisation

Our results indicate that argumentation can generally be conducive to polarisation, but that there are differences between argumentation strategies: 

![The general development of polarisation in the model.]({{ site.baseurl }}/assets/img/2022-02-02-general-development.png)

We use two algorithms to determine clusters in the population, the [Leiden algorithm](https://www.nature.com/articles/s41598-019-41695-z) by Traag, Waltman and van Eck, and [Affinity Propagation](https://www.science.org/doi/10.1126/science.1136800) by Frey and Dueck. The measure shown here, Group Divergence, is one of the cluster-based measures in Bramson et al.'s [paper on standard polarisation measures](https://www.tandfonline.com/doi/abs/10.1080/0022250X.2016.1147443).

It is also interesting to see how clusters build up and change throughout a model run. Although every argumentation strategy has a non-zero chance of facilitating low and high polarisation, *on average* they lead to quite different dynamics:

![How clusters form throughout a model run: Comparison of two strategies.]({{ site.baseurl }}/assets/img/2022-02-02-clusters.png)

The observed tri-polarisation in the “attack” model run is particularly interesting when compared to the very low clustering in the “convert“ strategy.

## What about de-polarisation?

We speak of *de-polarisation* when initial states of medium and high polarisation are reduced to lower states of polarisation. The paper also looks into polarisation dynamics for debates initialised with perfect bi-polarisation, that is, pre-configured clustering into two cohesive groups that are maximally distant to each other:

![Depolarisation effects following initial bi-polarisation.]({{ site.baseurl }}/assets/img/2022-02-02-depolarisation.png)

The observed effect confirms the results obtained above: while argumentation generally drives polarisation dynamics and can induce depolarisation among initially opposed agents, the effect very much depends on the argumentation strategy in use. Some argumentation strategies, “attack” and “fortify”, appear entirely unable to induce depolarisation in debates (in the figure, the “fortify” and “attack” plots overlap).