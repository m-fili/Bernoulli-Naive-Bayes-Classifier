# Bernoulli Naive Bayes Classifier

This project implements a Bernoulli Naive Bayes Classifier using tensorflow probability.

## Introduction
The Bernoulli Naive Bayes Classifier is a probabilistic machine learning model that applies Bayes' theorem with strong (naive) independence assumptions between the features.

## Methodology

The Bernoulli Naive Bayes Classifier is based on Bayes' theorem, which is formulated as:

$P(y|x_1, x_2, ..., x_n) = \frac{P(y) \prod_{i=1}^{n} P(x_i|y)}{P(x_1, x_2, ..., x_n)}$

Applying the total probability rule, we can express the denominator $P(x_1, x_2, ..., x_n)$ as:

$ P(x_1, x_2, ..., x_n) = \sum_{y} P(y) \prod_{i=1}^{n} P(x_i|y) $

which leads to the following equation:

$ P(y|x_1, x_2, ..., x_n) = \frac{P(y) \prod_{i=1}^{n} P(x_i|y)}{\sum_{y} P(y) \prod_{i=1}^{n} P(x_i|y)} $

Log probability can be computed as:

$ \log P(y|x_1, x_2, ..., x_n) = \log P(y) + \sum_{i=1}^{n} \log P(x_i|y) - \log \sum_{y} P(y) \prod_{i=1}^{n} P(x_i|y) $










## Dataset
The dataset used in this project is the `fetch_20newsgroups` dataset from the `sklearn.datasets` module. This dataset comprises around 20,000 newsgroups documents, partitioned across 20 different newsgroups. It is commonly used for text classification tasks.

## Examples


>Example 1:  
**True label:** comp.graphics  
**Predicted label:** comp.graphics  

**Content:**  
From: carlos@carlos.jpr.com (Carlos Dominguez)
Subject: Re: Where did the hacker ethic go?
Reply-To: carlos@carlos.jpr.com
Organization: Private Helldiver/Usenet system, Brooklyn, NY, USA
Lines: 38
X-Newsreader: Helldiver 1.07 (Waffle 1.65)

In <1sp4qj$243@dorsai.dorsai.org> crawls@dorsai.dorsai.org (Charles Rawls) writes:
The hacker ethic is ALIVE and WELL here.  I know of what you speak, and my
only answer is "SCREW 'EM".  You have to do what make you feel right.
amen.. I too have learned by example, specifically yours. :)
What can I say but keep the faith, there are others who do likewise.
.. but dorsai leads the way.. Unlike other services that are commercial
in nature, dorsai is a community based service. While others charge
monthly fees for access, dorsai accepts donations from those who can
afford to contribute.
    While other systems don't respond to user input, dorsai thrives on it.
Other systems sell hardware for a profit, dorsai donates hardware to
community service 


>Example 2:   
**True label:** rec.sport.baseball  
**Predicted label:** rec.sport.baseball  


**Content:**  
From: tedward@cs.cornell.edu (Edward [Ted] Fischer)
Subject: Re: Bases loaded walk gives Reds win in 12
Organization: Cornell Univ. CS Dept, Ithaca NY 14853
Lines: 87
In article <mssC5y5u0.4Dn@netcom.com> mss@netcom.com (Mark Singer) writes:

Actually, I think the large-scale sample size is part of the problem.
It seems to me that if we were to plot all the players in baseball
in regard to BA vs. Clutch BA deviation we would get some kind of
bell curve.  (The X-axis being the +/- deviation in clutch hitting
vs. non-clutch;  the Y-axis being the number of players.)  Certainly
there would be *some* players on the extreme ends of the bell.
Right.  Most definitely.
My *supposition* is that if we were to find the SAME players
consistently (year after year) at one end of the bell or the other,
then we might be able to make some reasonable conclusions about
*those* players (as opposed to all baseball players).
This may be the root of the confusion...
