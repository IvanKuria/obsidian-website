Class: [[STAT 131]]
Subject: #probability 
Date: 2025-02-11
Teacher: **Prof. Marcela

# Variance
- the [[variance]] of a random variable $X$ is
$$Var(X) = E(X - E(X))^2$$
- square root of variance is called Standard Deviation(SD)
$$SD(X) = \sqrt{Var(X)}$$


## Theorem
- For any random variable $X$,
$$Var(X) = E(X^2) - (E(X))^2$$

## Properties
- $Var(X + c) = Var(X)$ for any constant c
- $Var(cX) = c^2Var(X)$ for any constant c. Variance isn't linear
- If $X$ and $Y$ are independent, then $Var(X + Y) = Var(X) + Var(Y)$
- $Var(X) \geq 0$, with equality if and only if $P(X = a) = 1$ for some constant $a$.

## Geometric Distribution
- Let $X$ ~ $Geom(p)$. 
$$E(X) = \frac{q}{p}$$
$$Var(X) = \frac{q}{p^2}$$
## Negative Binomial Distribution
- must be independent and identically distributed(iid)
- Let $Y$ ~ $NBin(p)$. 
$$E(Y) = \frac{rq}{p}$$
$$Var(Y) = \frac{rq}{p^2}$$
## Binomial Distribution
  Let $X$ ~ $Bin(p)$. 
$$E(X) = np$$
$$Var(X) = np(1 - p)$$


# Poisson Distribution
- a random variable $X$ has the Poisson distribution with parameter $\lambda$, where $\lambda > 0$, if the PMF of $X$ is: $P(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}$, for $k = 0,1,2,...$ Written as $X$ ~ $Pois(\lambda)$ 
- The Poisson distribution is often used in situations where we are counting the number of success in a particular region or interval of time, and there are a large number of trials, each  with a small probability of success. Some examples of r.v.s that could follow a distribution  that is approx Poisson:  
	- Number of emails your receive in an hour. 
	- Number of chips in a chocolate chip cookie. 
	- Number of earthquakes in a year in some region of the world. 

- The parameter can be interpreted as the rate of occurrence of these rare events. 
- For *example* $\lambda = 20$ emails per hour, $\lambda = 10$ chips per cookie, $\lambda = 2$ earthquakes per year

## Variance for Poisson Distribution
- Let $X$ ~ $Pois(p)$. 
$$E(X) = \lambda$$
$$Var(X) = \lambda$$
