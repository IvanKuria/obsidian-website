Class: [[STAT 131]]
Subject: #probability 
Date: 2025-01-29
Teacher: **Prof. Marcela

# Binomial Distribution

## Formula
$$P(X = K) = \binom{n}{k}p^k(1-p)^{n-k}$$
n = # of independent trials
p = probability of success
k = target value
### Example
- It is known that *20%* of the students on campus don't have a TikTok account. If we collect a sample of $n = 100$ students, what is the probability of observing exactly *40* students that don't have a TikTok account?
- Also what is the probability of observing *30* students?

#### Explanation
1. Do we need assumptions? *Yes*
	- $n$ trials
	- independent
	- fixed $p$ (success: not having TikTok account, failure: having a TikTok account)

2. Identify the parameter values
	- $n$ = 100
	- $p$ = 0.2

3. What is the probability of interest?
	Formula: $P(X = K) = \binom{n}{k}p^k(1-p)^{n-k}$
	
	- P(X = 40) = $$\binom{100}{40}(0.2)^{40}(0.8)^{60} = 2.316e^-6$$
	- P(x >= 30) = 