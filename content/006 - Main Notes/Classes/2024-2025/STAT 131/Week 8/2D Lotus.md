---
title: "2D Lotus"
type: lecture
class: STAT 131
date: 2025-03-10
tags:
  - statistics
---

# 2D Lotus

## Theorem

### Discrete
- Let g be a function from $R^2$ to $R$. If X and Y are discrete, then:
$$E(g(X, Y)) = \sum_x \sum_y g(x, y)P(X=x, Y=y)$$
### Continuous
- If X and Y are continuous with a joint PDF fx,y then:
$$E(g(X, Y)) = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y)f_{X, Y}dxdy$$

### Example
![[stat131-2d-lotus-example.png|600]]
