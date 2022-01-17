---
layout: post
title: "Is it Rational to Stick to One's Beliefs?"
author: "Gregor Betz"
categories: journal
tags: [argumentation, social epistemology]
---

[📝 [Paper](http://philsci-archive.pitt.edu/20111/)] 

Doxastic conservativism is the idea that, when forced to change one's beliefs (e.g., because of novel evidence), one should retain as many previously held beliefs as possible. Yet, is this really a sensible policy? Or, couldn't it makes sense to revise one's position more drastically (than strictly required) in order to attain an overall better confirmed position given the new evidence? In this paper, we're studying -- with the help of a formal model and computer simulations -- whether it is truth-conducive to trade in previous beliefs for an evidentially better justified position. This post illustrates the paper's idea by means of a simple example.

## Two Strategies

Suppose there are two rival hypothesis, H1 and H2, that entail, given suitable auxiliary assumptions, two items of evidence, as specified below,

![SimpleMap]({{ site.baseurl }}/assets/img/2022-01-13-doxastic_conservativism_map1.png)

Let's further assume Ann and Betty have previously acquired evidence E1. They hold, moreover, identical positions in this dialectic context, considering as true:

* hypothesis H1, and
* auxiliary assumption A1;

and as false:

* hypothesis H2,
* auxiliary assumption A2, and
* evidence item E2 (necessarily so, cf. `<Arg 2>`).

|      | H1 | H2 | A1 | A2 | E1 | E2 |
|------|----|----|----|----|----|----|
|prior | t  | f  | t  | f  | t  | f  |


Starting from these identical positions, both Ann and Betty learn that E2 is the case. But they react to this novel evidence in different ways, illustrating two characteristic belief revision policies:

Ann, we shall suppose, just gives up her belief in auxiliary A1, this ensures that her new position is consistent.

Betty, in contrast, is willing to sacrifice further previously held beliefs. Upon learning that E2, she rejects hypotheses H1 and switches to H2, accepting in addition auxiliary A2. 

|      | H1 | H2 | A1 | A2 | E1 | E2 |
|------|----|----|----|----|----|----|
|prior | t  | f  | t  | f  | t  | f  |
|Ann   | t  | f  |**-** | f  | t  | **t**  |
|Betty | **f**  | **t**  | **-**  | **t**  | t  | **t**  |

Both Ann and Betty hold consistent posterior positions. Ann has made minimal changes to her prior. Yet, she now holds a hypothesis (H1) that is not confirmed (HD-account) by any available evidence. Betty, in contrast, revised her beliefs substantially and is now accepting a hypothesis (H2) that is confirmed by the evidence.   

Has anybody made a mistake? Which strategy is epistemically superior?


## Veritistic Evaluation

We assess conservative and justification-guided belief revision policies in a veritistic framework. That is, we study whether one rather than the other policy helps agents to track down the truth.

In a first step, the computational veritistic analysis gives us a mixed picture. All in all, neither strategy (conservatism or justification) seems to dominate the other in terms of acquiring many true beliefs. 

In a second step, however, we find and argue that -- from a collective perspective -- the less conservative, justification-seeking policy is clearly superior. We observe that justification-seeking agents in one and the same epistemic community substantially diverge in terms of how many posterior beliefs they hold. Moreover, it turns out that posterior belief content size correlates strongly with verisimilitude: Justification-seeking agents that hold many posterior beliefs are very likely to be close to the truth. In a justification-seeking, non-conservative community, all agents may hence finally adopt the agent position with maximal content size and thus **track down the truth collectively** much more effectively than communities of conservative agents.

This amounts to a social epistemic utility argument for justification-seeking belief revision policies and against doxastic conservativism.

## Status of the Paper

The paper has been submitted to a renowned PhilSci journal in May 2016, and the decision is still pending (as of Jan 2022). I've finally decided to make the manuscript available via a preprint server. 