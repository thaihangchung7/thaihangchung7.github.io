---
layout: notes
title: Statistics 
---

A collection of notes while I brush up on statistics.

Table of Contents
=================

   * [Binomial Distribution](#binomial-distribution)
   * [Poisson Distribution](#poisson-distribution)
   * [Gaussian Distribution](#gaussian-distribution)
   * [Methods of Counting](#methods-of-counting)
      * [The Birthday problem](#the-birthday-problem)


# Uncertainty Statistics

The measured value is given by: $$x_{m} = x_{avg} \pm \Delta x_{avg}$$

## Uncertainty in a Measurements
For small data sets:

$$\Delta x = \frac{x_{max}-x_{min}}{2}$$

For large data sets:

$$\Delta x = \sigma = \sqrt{ \frac{\sum_{i=1}^{N} (x_{i} - x_{avg})^{2}}{N} }$$

## Uncertainty in the Mean

For small data sets:

$$\Delta x_{avg} = \frac{\Delta x}{\sqrt{N}}$$

For large data sets:

$$\Delta x_{avg} = \frac{\sigma}{N}$$

## Binomial Distribution
For a binomial distribution with parameters $$n$$ and $$p$$ the discrete probability distribution of the number of occurences $$k$$ in an sequence of $$n$$ independent experiments is given by: 

$$ P(k: n, p) = {n \choose k} p^{k} (1 - p)^{n-k} $$

If $$X ~ B(n,p)$$, then we can say that the expectation value of $$X$$ is:

$$E[X]=np$$

## Poisson Distribution
If $$n$$ is sufficiently large and $$p$$ is sufficently small, the Poisson distribution with paramenter $$\lambda = np$$ can be used to approximate $$B(n,p)$$

$$Poisson(k;\lambda) = \frac{\lambda^{k} e^{-k}}{k!}$$

If $$X ~ Poisson(k;\lambda)$$ then the $$\lambda$$ is equal to the expectation value and variance:

$$\lambda = E[X] = Var[X]$$

## Gaussian Distribution
Now let's take the discrete $$k$$ to infinity and replace k with a continuous parameter $$x$$. Using Stirling's approximation, $$\ln n! = n\ln n - n$$...

$$P(x) = G(x, \sigma = \sqrt\lambda ) = \frac{1}{2 \pi \sigma} e^{ -( x - \lambda )^2 / 2\sigma^{2}} $$


### The Birthday problem
Suppose you randomly select two people from a room. What is the probability that those people have the same birthday? 

A quick google search of "the birthday problem" will show that this quite a famous problem and leads to an intriguing  solution. Let's work it out:

TODO: show that at around 23 people, the likelyhood of two people having the same birthday is 1/2

# Curve Fitting Basics

## Least Squares 

For some experimental data $$x_{exp}$$ and $$y_{exp}$$, find a function $$y = f(x,\beta)$$ that best resembles the data. $$\beta$$ is a set of unknown parameters that is adjusted to perform said task. The method of least squares can be stated as 

$$ \sum_{i} (f(x_{i},\beta) - y_{i})^{2} $$ 

where $$x_{i}$$ and $$y_{i}$$ are the data points.

## $$\chi^{2}$$ Testing

$$ \chi^{2} = \frac{\sum_{i} (y - y)^{2}}{\sigma^{2}} $$
