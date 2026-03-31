---
title: "Moments"
type: lecture
class: STAT 131
date: 2025-02-24
tags:
  - statistics
---

# Moment Generating Functions(MGF)

## Geometric MGF
- For $X$ ~ $Geom(p)$,
$$M(t) = E(e^Xt) = \frac{p}{1 - e^tq}$$
- for $qt$ < 1, i.e for t in $(-\infty, log(1/q))$ 

## Uniform MGF
- for $U$ ~ $Unif(a, b)$
$$M(t) = E(e^Ut) = \frac{e^tb - e^ta}{t(b-a)}$$
- for $t \neq 0$ and $M(0) = 1$

## Sum of Independent R.V's
- MGFs of a sum of independent r.v.s. If $X$ and $Y$ are independent, then the MGF of $X + Y$ is the product of the individual MGFs:
$$M_{X+Y}(t) = M_X(t)M_Y(t)$$
- This is true because if $X$ and $Y$ are independent, then $$E(e^t{(X+Y)} = E(e^tX)E(e^tY))$$

## MGF of location-scale transformation.
-  if $X$ has MGF $M(t)$, then the MGF of $a + bX$ is:
![[stat131-mgf-location-scale-transformation.png]]
