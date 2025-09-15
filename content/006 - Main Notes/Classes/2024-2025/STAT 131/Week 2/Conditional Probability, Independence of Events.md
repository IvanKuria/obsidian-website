Class: [[STAT 131]]
Subject: #probability 
Date: 2025-01-21
Teacher: **Prof. Marcela**

# Conditional Probability
- given $A$ and $B$ are events with $P(B) > 0$, the the [[conditional probability]] of $A$ given $B$, denoted by $P(A|B)$, is defined as:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

### Example
- Standard deck: *52 cards* that are shuffled.
- *2* cards are drawn randomly, one at a time without replacement.
- Let $A$ be the event that the first card is a heart.
- Let $B$ be the event that the second card is red.
- Find $P(A|B)$ and $P(B|A)$. *Are they equal?*

Using the naive definition of probability and the *multiplication rule*:
$$P(A \cap B) = \frac{13 * 25}{52 * 51} = \frac{25}{204}$$
*note*: we use 25/51 because the first card would be red resulting in one less red card in the deck.
$P(A) = \frac{1}{4}$ and $P(B) = \frac{1}{2}$

$$P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{25/204}{1/2} = \frac{25}{102}$$

## Bayes' Rule
- Probability of the intersection of two events. For any events $A$ and $B$ with positive probabilities:
$$P(A \cap B) = P(B)P(A|B) = P(A)P(B|A)$$

# Independence of Events
- Events $A$ and $B$ are independent if
$$P(A \cap B) = P(A)P(B)$$
- If $P(A) > 0$ and $P(B) > 0$, then this is equivalent to:
$$P(A|B) = P(A)$$
- which is also equivalent to:
$$P(B|A) = P(B)$$
- Basically, if non of the events have no effect on each other, than they are *independent*

## Proposition
- If $A$ and $B$ are independent, then $A$ and $B^c$ are independent, $A^c$ and $B$ are independent, and $A^c$ and $B^c$ are independent.
$$P(B^c|A) = 1−P(B|A) = 1 − P(B) = P(B^c)$$

$P(D_1 \mid W) = \frac{P(D_1 \cap W)}{P(W)}$ 

$$w_o * P(D_1^c)*P(D_2^c) + 1 * P(D_1 \cup D_2)$$
$$=$$
$$w_o * (1 - p_1)(1 - p_2) + p_1 + p_2 - p_1 * p_2$$
$$=$$
$$w_o * (1 - p_1)(1 - p_2) + P(D_1)+P(D_2) - P(D_1 \cap D_2)$$
$$P(both \ girls \ \cap \ at \ least \ one \ c) = P(at \ least \ one \ C \mid both \ girls) * P(both \ girls)$$
$$=$$
$$1 - P(no \ C \mid both \ girls) = 1 - (1 - p)(1 - p) = 1 - (1 - p)^2$$
$$=$$
$$0.25 * (1 - (1 - p)^2) = 0.25 * p(2 - p)$$
$$P(D_1 \mid W)P(D_2 \mid W) = \frac{p_1}{P(W)}*\frac{p_2}{P(W)}*\frac{p_1p_2}{P(W)}$$
Because $P(D_1 \cap D_2 \mid W) = P(D_1 \mid W)P(D_2 \mid W)$ ,  D_1  and  D_2  are conditionally independent given  W

  

$$P(W) = P(W \mid D_1 \cup D_2)P(D_1 \cup D_2) = 1 \cdot (p_1 + p_2 - p_1p_2)$$
Because $P(D_1 \cap D_2 \mid W) = P(D_1 \mid W)P(D_2 \mid W)$, conditional independence is still observed