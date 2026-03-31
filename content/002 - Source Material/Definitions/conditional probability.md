---
title: "Conditional Probability"
type: definition
domain: statistics
aliases: [conditional probabilities]
tags:
  - definition
---

Given $A$ and $B$ are events with $P(B) > 0$, the conditional probability of $A$ given $B$, denoted by $P(A|B)$, is defined as:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

## Context

Conditional probability is foundational in statistics and machine learning. For example, if 30% of emails are spam and 80% of spam emails contain the word "free," then $P(\text{contains "free"} | \text{spam}) = 0.80$. Bayes' theorem builds directly on conditional probability.

## See Also

- [[event]]
- [[sample space]]
- [[variance]]
