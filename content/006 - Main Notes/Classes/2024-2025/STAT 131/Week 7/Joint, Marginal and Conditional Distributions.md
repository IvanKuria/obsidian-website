---
title: "Joint, Marginal and Conditional Distributions"
type: lecture
class: STAT 131
date: 2025-02-24
tags:
  - statistics
---

# Discrete
## Joint

### Joint CDF
- Joint CDF. The joint CDF of r.v.s $X$ and $Y$ is the function $F_{X, Y}$ given by:
$$F_{X, Y}(x, y) = P(X \leq x, Y \leq y)$$
### Joint PMF
- Joint PMF of a discrete r.v.s X and Y is the function px,y given by
$$\mathbb{p}{x,y}(x, y) = P(X = x, Y = y)$$
- If X and Y are independent, then pxy(x, y) = px(x)py(y)

## Marginal

### Marginal PMF
- for discrete r.v.s X and Y, the marginal PMF of X is:
$$P(X=x) = \sum P(X=x, Y=y)$$

### Conditional PMF
 - for conditional r.v.s X and Y, the conditional PMF of Y is given as X = x is:
$$P(Y=y | X=x) = \frac{P(X=x|Y=y)}{P(X=x)}$$

## Example
![[stat131-joint-distributions-01.png]]

a) $$P(X = 0, Y=0) + P(X = 0, Y=1) = 1/6 + 1/4 = 5/12$$
b) 
$$P(Y = 0) = 1/6 + 1/8 = 7/24$$
$$P(Y = 1) = 1/4 + 1/6 = 5/12$$
$$P(Y = 2) = 1/8 + 1/6 = 7/24$$
![[stat131-joint-distributions-02.png|400]]
*If they don't sum up to 1, then you made a mistake somewhere!*

c) $$P(Y = 1|X = 0) = \frac{P(Y=1,X=0)}{P(X=0)}$$
$$P(Y = 1, X = 0) = 1/4$$
$$P(X = 0) = 13/24$$
 = $$\frac{1/4}{13/24} = 6/13$$
d) Just show that for some $P(X=x, Y=y) \neq P_X(x)*P_Y(y)$ 
$$P(X=0, Y=0) \neq P_X(0)*P_Y(0)$$ because
$$1/6 \neq 13/24*7/24$$ 
# Continuos

## Joint

### Joint PDF
- if X and Y are continuous, their joint PDF is the derivative of the joint CDF with respect to x and y:
![[stat131-joint-distributions-03.png|400]]

#### Example
$$P(X < 3, 1 < Y, 4) = \int_1^4\int_{-\infty}^3f_{X, Y}(x, y)dxdy$$

## Marginal

### Marginal PDF
- for continuous r.v.s X and Y with joint PDF fx,y, the marginal PDF of X is:
![[stat131-joint-distributions-04.png | 400]]

## Conditional

### Conditional PDF
- for continuous r.v.s X and Y with joint PDF fx,y, the marginal PDF of Y given X=x is:
![[stat131-joint-distributions-05.png|400]]

## Example
![[stat131-joint-distributions-06.png]]

b) ![[stat131-joint-distributions-07.png|600]]
$$c/10 = 1, c = 10$$

c)![[stat131-joint-distributions-08.png]]

 d) ![[stat131-joint-distributions-09.png]]

e) $$= \frac{P(Y\leq x/4, Y \leq x/2)}{P(Y \leq x/2)} = 4P(Y\leq x/4)$$
*we ignore $Y \leq 2$ because* 
![[stat131-joint-distributions-10.png|400]]

![[stat131-joint-distributions-11.png|500]]
