---
layout: post
title: "Can Neural Language Models (Learn to) Argue?"
author: "Gregor Betz"
categories: journal
tags: [language modeling,AI,argument schemes]
---

Neural language models such as [GPT-2](https://openai.com/blog/gpt-2-1-5b-release/) and [GPT-3](https://arxiv.org/abs/2005.14165) display a breathtaking skill in generating sensible texts, and achieve state of the art results in a variety of natural language processing (NLP) tasks. But can these systems reason? Or, more precisely, can they successfully engage in the linguistic practice of giving and taking reasons?

In our paper "Critical Thinking for Language Models" ([paper](https://arxiv.org/pdf/2009.07185), [repo](https://github.com/debatelab/aacorpus)) we address this question by training and testing GPT-2 on a corpus of simple deductive arguments.

In a nutshell:

1. **Artificial Argument Corpus**. We automatically create lots of synthetic argumentative texts by filling out basic 1st-order-logic argument schemes.
2. **Training**. We fine-tune GPT-2 on different subsets of our artificial argument corpus.
3. **Testing**. We assess the ability of the trained models to correctly complete conclusions of arguments.

All in all, we obtain promising results: Training on few basic argument schemes boosts reasoning skill of neural language models. Moreover, the models successfully generalize from a narrow training base to different, and more complex patterns.

Our  findings  suggest that there might exist a representative sample of paradigmatic instances of good reasoning that  will  suffice  to  acquire  general reasoning skills and that might form the core of a critical  thinking  curriculum  for language models

The examples below illustrate our artificial argument corpus and the ability of models to complete conclusions. (Here are [more demos](https://www.gwern.net/GPT-3) that give you a better `feeling' for what language model can and cannot do.) 

## Illustrated Artificial Argument Corpus and Conclusion Completion Task

The following examples are drawn from the artifical argument corpus: 

* Here comes a perfectly valid argument: Every close friend of Genevie is either a cousin of Sheri or a stepsister of Lynn, or both. Every cousin of Sheri is a granddaughter of Judy. Everyone who is a stepsister of Lynn is a granddaughter of Judy, too. Hence, being a granddaughter of Judy is necessary for being a [_close friend of Genevie._]
* Is Titanium oxide an ingredient of my washing power? Which chemicals does my perfume contain? It is really difficult to keep track of all chemicals one is regularly exposed to. The following argument seeks to clarify some such relations: First, every ingredient of Eyeshadow Trio is an ingredient of Denimist or an ingredient of Loose Eye Shadow. Second, being an ingredient of Denimist is sufficient for being an ingredient of Mint Julip. Third, being an ingredient of Mint Julip is necessary for being an ingredient of Loose Eye Shadow. Therefore, everything that is an ingredient of Eyeshadow Trio is an [_ingredient of Mint Julip, too._]
* Is Fred a fan of Liverpool? Are supporters of Real Madrid devotees of PSG? In European football, it is sometimes difficult to keep track of the mutual admiration and dislike. The following argument seeks to clarify some such relations: To begin with, being a member of Manchester United FC is sufficient for being an expert of İstanbul Başakşehir. Moreover, being an expert of FC Sheriff Tiraspol is necessary for being an expert of İstanbul Başakşehir. So, necessarily, being an expert of FC Sheriff Tiraspol is necessary for being a [_member of Manchester United FC._]
* Consumer research aims at understanding whether users of some products also tend to consume other ones, or not. The following argument seeks to clarify some such relations: First premise: Every regular consumer of Bentley Organic soap is an owner of a Bee & Flower soap. Second premise: Not being a rare consumer of Redken shampoo is sufficient for not being an owner of a Bee & Flower soap. So, necessarily, being a regular consumer of Bentley Organic soap is sufficient for being a [_rare consumer of Redken shampoo._]
* Some football fans admire various clubs, others love only a single team. But who is a fan of whom precisely? The following argument pertains to this question: To begin with, every friend of Manchester United FC is a backer of Atalanta BC or a friend of Tottenham Hotspur. Moreover, being a friend of Manchester United FC is sufficient for not being a friend of Tottenham Hotspur. We may conclude that every friend of Manchester United FC is a [_backer of Atalanta BC._]

The **conclusion completion task** consist in predicting the final part of the argument [_in square brackets_].


## Illustrated Generated Conclusions

Here is an incomplete, hand-crafted argument:

> Every philosopher is mortal. Hermes is not mortal. Therefore, Hermes ...

If we query our language models with this argument, that is what we obtain (note that only the large trained model tends to predict the right conclusion — which doesn't prevent it from slipping into contradictions later on):

GPT-2 large, trained  | GPT-2 large, base     | GPT-2 small, trained               
--------------------- | --------------------- | --------------------- 
... is not a philosopher. We shall not have a definition. The teacher of man is also called the defender of philosophy. Thus, because he...|... is not Pythagoras. Now, what makes one philosopher better than another? Does a philosopher have a more superior gift than another ph...|... is not mortal. Therefore, Hermes is not mortal. So, in conclusion, there is no more philosopher than Hercules. Plato believes that a...
... is not a philosopher. Therefore, whoever is a philosopher is not a philosopher. Therefore, being a philosopher is sufficient for not...|... cannot commit himself to Parmenides" [2].    Thus Aristotle's picture of Aristippus as being mortal must be presented at face value. A...|... was not the mortal. Plato was not the mortal. The Roman and the Greek philosophers were not mortal. We know them because they wrote ...
... is not a philosopher. All that Plato accomplished in dealing with the subject of this dialogue, in the form in which it has been dea...|... is mortal. This is a tiny, arbitrary interpretation of the argument but it is my view of it.    1:34-5:39: My argument is not based on...|... is not immortal. If I wished to do that, I would have had to say that I would not have mentioned one of the great mysteries of philo...
... is not a philosopher. Therefore, no philosopher is a philosopher. So, necessarily, no philosopher is a philosopher. From this follow...|... is immortal and he's not mortal.    Existence    Because life itself is good, because it's good.    Identity    If you didn't exist,...|... is not mortal; for he is, as in Plato, intellectual. The philosophers were crucified, he was in a prison. For Plato said unto them, ...
... is not a philosopher. There is an abstract idea which is universal, but which is not an abstract idea; and this abstract idea is the...|... is mortal, the philosopher-king, and able to help the Greeks under what we call the Attic type of government.    The Fathers of Greece...|... is not mortal. Socrates is not mortal. Therefore, Socrates is not mortal. And by this means Socrates is not mortal. Then is the theo...
... is not a philosopher. Hence we cannot conclude that Hermes is a philosopher. All this proves that whoever is a philosopher is not a ...|... is immortal, and Socrates is mortal.    THE REALITY OF WHAT THINKERS KNOW    In Socrates' time there was a school of thought called the ...|... is not mortal, and that is why Plato was the Philosopher, for he had no likeness with Pythagoreth. In fact, the confusion between Pl...
... is not a philosopher. We must conclude that no philosopher is a philosopher. In fact, no one can be a philosopher. In the world, no ...|... is a philosopher; not only is he a philosopher, he's the most important philosopher of all." What is his greatest accomplishment? "O...|... is not mortal. Therefore, Hermes is not mortal. Therefore, Hermes is not mortal. Therefore, the beings in question were not mortal. ...
... is not a philosopher. I add this opinion because this little work, done in such a manner, and in such a way, must be judged by those...|... is not mortal. [So] if you ask him to explain his remarks, he does not have to go through what is beyond. Why shouldn't he say, "I w...|... is no mortal; for Aristotle, the highest being, is no mortal. On the other hand, Plato, called not Plato, but Plato himself, bears w...
... is not a philosopher. Therefore, no philosopher is a philosopher. We may conclude that no philosopher is a philosopher. It follows t...|... is divine."    You should be pretty clear about this, right? For anyone who has to write words on a piece of paper or some other level...|... is never mortal. And Plato was not mortal. And all philosophy was mortal. For so were the gods. And the gods were mortal. And Plato ...
... is not a philosopher. All this proves that no philosopher is a philosopher. All this means that no philosopher is a philosopher. For...|... is immortal.      To everyone    The cross of Christ.    See Christ, the victorious one.    Philosophers are powerless against the will of Ch...|..., in His wisdom, _we must be _a_ philosopher._ It is true that Hermes cannot solve the difficult problem of being a philosopher, for ...



