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


# Statistical Treatment of Experimental Data

## Cumulative Distribution

Suppose we want to know the probability of finding $$x$$ between some interval $$x_{1}$$ and $$x_{2}$$, in other words:

$$ P(x_{1}\leq x \leq x_{2})$$

If $$P(x)$$ is assumed to be continuous, then,

$$ P(x_{1}\leq x \leq x_{2})=\int_{x_{1}}^{x_{2}} P(x) dx$$

If discrete, then:

$$ P(x_{1}\leq x \leq x_{2})=\sum_{i = 1}^{2} P(x_{i})$$

Of course, normalization applies to these distributions,

$$\int P(x) dx = 1$$ (Continuous) 

$$\sum_{i} P(x_{i}) = 1$$ (Discrete)

# Distribution Moments: Mean and Variance

A probability distribution can be characterized by it's mean ($$\mu$$) and variance ($$\sigma$$), also known as _moments_ of the distribution.

Moments in a statistical distribution draws parallels to mass distributions in mechanics. For example, the mean represents the "center of mass" of the probability distribution. The variance, represents the width or spread of the distribtion, which gives an idea of how much a random variable $$x$$ fluctuates about the mean. Mathematically,

$$ \mu = E[x] = \int x P(x) dx $$

$$ \sigma^{2} = E [(x - \mu)^{2}] = \int (x-\mu)^{2} P(x) dx $$ 

## Uncertainty in Statistics

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

## Covariance

Consider a multivariate distribution,  $$ P(x,y,z,...)$$, where the outcome depend on several random variables $$x,y,z,...$$. The random variables of the multivariate distribution can be indiviually defined by the mean and variance in addition to  the covariance. 
The covariance measures the linear correlation of two variables using the correlation coefficient.

$$ \rho = \frac{cov(x,y)}{\sigma_{x} \sigma_{y}} $$

If $$\|\rho\|=1$$, then the variables are linearly correlated. Otherwise, if the coefficient varies between $$-1$$ and $$+1$$, this indicates a negative or positive correlation, respectively.




# Common Probability Distributions

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

## $$\chi^{2}$$ "Goodness of Fit"

$$\chi^{2} = \bigg( \frac{O_{i} - E_{i}}{\sigma_{i}} \bigg)^{2} $$

Here, $$O_{i}$$ represents the observed data, $$E_{i}$$ is the expected value of $$i$$, and $$\sigma_i$$ is the y-axis standard deviation of $$O_{i}$$.

We can modify the $$\chi^{2}$$ slightly to quantify the difference between two curves based on their known standard deviations. In this case, the standard deviation of the difference need to be taken into account, 

$$ \sigma_{diff} = \sqrt{ (\sigma_{i}^{a})^{2} + (\sigma_{i}^{b})^{2}  }$$

Subsequently,

$$\chi_{diff}^{2} = \bigg( \frac{O_{i}^{a} - O_{i}^{b}}{\sigma_{i,diff}} \bigg)^{2} $$

In words, the statistical significance between two curves.

