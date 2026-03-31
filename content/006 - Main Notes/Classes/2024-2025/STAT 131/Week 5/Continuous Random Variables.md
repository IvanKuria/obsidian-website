---
title: "Continuous Random Variables"
type: lecture
class: STAT 131
date: 2025-02-11
tags:
  - statistics
---

# Continuous Random Variables

- An r.v. has a continuous distribution if its CDF is differentiable. We also allow there to be endpoints (or finitely many points) where the CDF is continuous but not differentiable, as long as the CDF is differentiable everywhere else. A continuous r.v. is a random variable with a continuous distribution. 

## Examples 
- Temperature at a certain location 
- Age as a continuous measure: 25 years, 10 months, 2 days, 5 hours, 4 seconds, 4 milliseconds, 8 nanoseconds, 99 picoseconds … and so on. 
- *Intuition*: Things that could take you forever to count

## PDF
- For a continuous r.v. with CDF , the probability density function ([[PDF]]) of is $X$ the derivative of the CDF, given by
$$f(x) = F^\prime(x)$$
To go from *PDF* to *CDF*,
$$F(x) = \int_{-\infty}^xf(t)dt$$
### Visual Representation
![[stat131-continuous-rv-01.png]]

### Problem 1:
- Let be a continuous random variable with the following PDF
![[stat131-continuous-rv-02.png]]

- where c is a positive constant
	- Find $c$ 
	- Find the CDF of $X$, $F_X(x)$
	![[stat131-continuous-rv-03.png]]
	- Find $P(1 < X < 3)$
	![[stat131-continuous-rv-04.png]]


## Expectation
$$E(X) = \int_{-\infty}^{\infty}xf(x)dx$$

- *Note*: may not exist

### LOTUS
$$E(g(x)) = \int_{-\infty}^{\infty}g(x)f(x)dx$$
# Uniform Distribution
- denoted by $U$∼$Unif(a,b)$
![[stat131-continuous-rv-05.png]]

## CDF
$$F_X(x) = \frac{x}{b - a}$$
## Expectation
$$E(U) = \frac{b + a}{2}$$
## Variance
$$E(U^2) = \frac{(b - a)^2}{12}$$
## Problem 1
- Let X be a continuous random variable with [[PDF]]
![[stat131-continuous-rv-06.png]]
- show that this is a valid PDF
![[stat131-continuous-rv-07.png]]
- Find the CDF
![[stat131-continuous-rv-08.png]]
- Find the mean and variance of $X$
![[stat131-continuous-rv-09.png]]
![[stat131-continuous-rv-10.png]]
