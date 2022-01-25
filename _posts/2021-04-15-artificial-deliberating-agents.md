---
layout: post
title: "Natural-Language Multi-Agent Simulations of Argumentative Opinion Dynamics"
author: "Gregor Betz"
categories: journal
tags: [language modeling,AI,opinion dynamics]
---

[📝 [Paper](https://www.jasss.org/25/1/2.html)] 
[[<i class="fa fa-github"></i> Code](https://github.com/debatelab/ada-simulation)]

In our recent paper, we develop a *natural-language* agent-based model of argumentation (ABMA). Its artificial deliberative agents (ADAs) are constructed with the help of so-called neural language models recently developed in AI and computational linguistics (and which we've explored [here]({{ site.baseurl }}/journal/thinking-aloud.html) and [here]({{ site.baseurl }}/journal/critical-thinking-language-models.html)). ADAs are equipped with a minimalist belief system and may generate and submit novel contributions to a conversation. 

![Sketch of artificial deliberating agents (ADAs)]({{ site.baseurl }}/assets/img/ADA_illustrated2.png)

The natural-language ABMA allows us to simulate collective deliberation in English, i.e. with arguments, reasons, and claims themselves -- rather than with their mathematical representations (as in formal models). 

We use the natural-language ABMA to test the robustness of formal reason-balancing models of argumentation [Maes & Flache 2013, Singer et al. 2019]: First of all, as long as ADAs remain passive, confirmation bias and homophily updating trigger polarization, which is consistent with results from formal models. However, once ADAs start to actively generate new contributions, the evolution of a conversation is dominated by properties of the agents *as authors*. This suggests that the creation of new arguments, reasons, and claims critically affects a conversation and is of pivotal importance for understanding the dynamics of collective deliberation. 

You can explore the simulation runs with our [streamlit app](https://share.streamlit.io/debatelab/ada-inspect/main/app.py):


![Streamlit App to Explore ADA Simulations]({{ site.baseurl }}/assets/img/screenshot_ada-inspect.png)

The paper has been published with [JASSS](https://www.jasss.org/), the preprint is still available [here](https://arxiv.org/abs/2104.06737).