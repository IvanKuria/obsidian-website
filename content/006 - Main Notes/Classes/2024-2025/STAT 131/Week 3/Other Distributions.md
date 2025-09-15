Class: [[STAT 131]]
Subject: #probability 
Date: 2025-01-29
Teacher: **Prof. Marcela**

# Hypergeometric Distribution

## Formula

$$P(X = K) = \frac{\binom{s}{k}\binom{f}{n-k}}{\binom{s+f}{n}}$$
- *Population* = $s + f$
- *Sample* = $n$ ($k$ and $n - k$)

### Example
- Items in a population are classified using two sets of tags: success and failure, or tagged not tagged, or two ball colors in an urn. 
- Example: You have an urn with $N = 10$ balls, $s = 6$ that are tagged as winners and $f = 4$ that are not. You take a sample of $n = 3$ balls, *without replacement*. What is the probability of observing $k = 2$ tagged balls on your sample?

#### Explanation
$$P(X = 2) = \frac{\binom{6}{2}\binom{4}{3-2}}{\binom{6+4}{3}} = 0.5$$
$$P(X \leq 2) = P(X = 0) + P(X = 1) + P(X = 2)$$
$$=$$
$$\frac{\binom{6}{0}\binom{4}{3-0}}{\binom{6+4}{3}} + \frac{\binom{6}{1}\binom{4}{3-1}}{\binom{6+4}{3}} + \frac{\binom{6}{2}\binom{4}{3-2}}{\binom{6+4}{3}} = 0.03333 + 0.03 + 0.05 = 0.83333$$

# Uniform Distribution
## Formula
$$P(X = x) = \frac{1}{\mid{C}\mid}$$

### Example
- A raffle. You have 100 possible numbers, $X$ is a random variable that represents  
the number that you select for the raffle, randomly
$$P(X = 8) = \frac{1}{100}$$

# PMF and CDF

### Example
- Given the following:
	![[Pasted image 20250129181052.png]]
a)  What is the support of $x$?
	{ 0, 1, 2}
b) Find $P(x \geq 1.5)$
	$$P(x \geq 1.5) = P(X = 2) = \frac{1}{2}$$
c) Find $P(0 < x < 2)$
	$$P(0 < x < 2) = P(x = 1) = \frac{1}{3}$$
d) Find $P(x = 0 \mid x < 2)$
	$$\frac{P(x = 0 \ \cap x < 2)}{P(x < 2)} = \frac{P(x = 0)}{P(x < 2)} = \frac{\frac{1}{2}}{\frac{5}{6}} = 3/5$$
