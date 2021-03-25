---
layout: post
title: "Thinking Aloud: Dynamic Context Generation Improves Zero-Shot Reasoning Performance of GPT-2"
author: "Gregor Betz"
categories: journal
tags: [language modeling,AI,deduction]
---

Thinking Aloud is well-studied and widely used meta-cognitive strategy to improve one's reasoning skill. In our paper ["Thinking Aloud: Dynamic Context Generation Improves Zero-Shot Reasoning Performance of GPT-2"](http://arxiv.org/abs/2103.13033) we explore whether neural language models like [GPT-2](https://openai.com/blog/gpt-2-1-5b-release/) can similarly (self-)improve their performance on a reasoning task by elaborating the problem before providing an answer. 

![Basic design of the thinking aloud study]({{ site.baseurl }}/assets/img/thal_first_example.png)

We create a simple multi-hop deductive inference task and evaluate various "elaboration strategies," e.g., by including different sample elaborations in the prompt, or by querying the model iteratively.    

Our main findings are:

* GPT-2 seems to follow a simple syntactic heuristic when solving our multi-hop inference task. This heuristic leads the model astray if the problem is sufficiently hard, causing fallacious reasoning and systematic bias.
* Self-generated problem elaborations can de-bias the system and increase accuracy by up to 8% for hard problems.
* The effectiveness of a given problem elaboration seems to depend on how well the elaboration coheres with the original problem description. (Most-faithful elaborations boost accuracy by up to 24%.) 

As a follow-up to this study, we're thinking about how a neural language model might acquire (be taught) the general competence to effectively and sensibly elaborate on a given problem. 

