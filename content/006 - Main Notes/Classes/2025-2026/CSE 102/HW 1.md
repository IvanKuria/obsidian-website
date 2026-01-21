
## 1.2-2
*n > 0*
 = $8n^2 \;<\; 64\,n \log n$ 
 = $\frac{8n^2}{8n} \;<\; \frac{64n\log n}{8n} \quad=\quad n \;<\; 8\log n$ 
 - here we can test a variety of n values to see where the switch happens and since we're using base 2 we can test with base 2 values(i.e. $n = 32$)

- 1. $n=32: \log_2(32)=5 \Rightarrow 8\log_2(32)=40$  which holds true becase $32 < 40$
- 2. $n=64: \log_2(64)=6 \Rightarrow 8\log_2(64)=48$ which doesn't hold true because $64 < 48$
- this means the n value we want is between 32 and 64. 
- at $n = 43$: $8(43^2)=8(1849)=14792$(**insertion**), $64\cdot 43\cdot \log_2(43) \approx 14933$(**merge**) and $14792 < 14933$ which holds true
- at $n = 44$: $8(44^2)=8(1936)=15488$(**insertion**) $\approx 64\cdot 44\cdot 5.459 \approx 15374$(**merge**) and $15488 < 15374$ which doesn't hold true.

- the value of n where insertion sort beats merge sort is $n = 43$

## 1.2-3

= $100n^2 < 2^n$
- here we have to experiment with different values of n
1. $n = 10$: $$100n^2 = 100\cdot 10^2 = 100\cdot 100 = 10{,}000 < 2^{10} = 1{,}024$$ which is **false**
2. $n = 13$: $$100n^2 = 100\cdot 13^2 = 169\cdot 100 = 16{,}900 < 2^{13} = 8{,}192$$ which is also **false**
3. $n = 14$: $$100n^2 = 100\cdot 196 = 19{,}600 < 2^{14} = 16{,}384$$ which is also **false**
4. $n = 15$: $$100n^2 = 100\cdot 225 = 22{,}500 < 2^{15} = 32{,}768$$ which holds true

- so the smallest value of $n$ such that an algorithm whose running time is $100n^2$ runs faster than an algorithm whose running time is $2^n$ on the same machine is $n = 15$ 

## 1.1-1
- my real world example that requires sorting is usually when I'm playing Old Maid(a card game) which requires that I have a standard deck of planning cards but sometimes we mix our cards which forces me to sort them. 
- one that requires finding the shortest distance between 2 points is whenever I need directions from my apartment to campus or going from my bedroom to the mailbox at my apartment.

## 2.1-1
1. $\boxed{31}\;\;41\;\;59\;\;26\;\;41\;\;58$ - first element already sorted for us
2. $\boxed{31\;\;41}\;\;59\;\;26\;\;41\;\;58$ - same for the second element
3. $\boxed{31\;\;41\;\;59}\;\;26\;\;41\;\;58$ - same for the third element
4. $\boxed{26\;\;31\;\;41\;\;59}\;\;41\;\;58$ - her we insert 26 at the front as it's the smallest element we've seen
5. $\boxed{26\;\;31\;\;41\;\;41\;\;59}\;\;58$ - here we insert 41 after the 41 we had already seen
6. $\boxed{26\;\;31\;\;41\;\;41\;\;58\;\;59}$ - here we insert 58 between 41 and 59

## 2.1-2
**Loop Invariant**: At the start of each iteration $i$, the variable **sum** equals the sum of the first $i-1$ elements of the array

Before the loop starts ($i=1$), sum = 0, which is the sum of zero elements.

We also knwo that each iteration adds $A[i]$ to sum, so it eventually becomes the sum of the first $i$ elements.

When the loop ends ($i=n+1$), sum contains the sum of all elements in $A[1..n]$.

## 2.1-4
``` python
for i = 1 to n
    if A[i] == x
        return i
        
return NIL
```

- **Loop Invariant**: At the start of each iteration $i$, the value $x$ does not appear in $A[1..i-1]$.
- Before the first iteration ($i=1$),  $A[1..0]$ is empty, so $x$ could not have appeared yet.
- If $x \neq A[i]$, then once we check $A[i]$, $x$ still does not appear in $A[1..i]$, so the invariant holds true for the next iteration.
- If the loop gets to $x$, it returns the index we want. If the loop ends without getting $x$, then $x$ does not appear in $A[1..n]$, so returning NIL is ok.


## Prove from the definitions of set union, intersection, complement and equality that

Let's let $x$ be any element.

To show the two sets are equal, we have to ensure tht they contain the same elements.

Let $x$ be any element.

$$
x \in \overline{A \cap B}
$$

$$
\iff x \notin A \cap B
$$

$$
\iff x \notin A \text{ or } x \notin B
$$

$$
\iff x \in \overline{A} \text{ or } x \in \overline{B}
$$

$$
\iff x \in \overline{A} \cup \overline{B}
$$

Since both sets contain the same elements,

$$
\overline{A \cap B} = \overline{A} \cup \overline{B}
$$
## Prove by induction on n


$$
\overline{\bigcap_{i=1}^{n} A_i} = \bigcup_{i=1}^{n} \overline{A_i}
$$

**Base case n = 1 :**
$$
\overline{A_1} = \overline{A_1}
$$

This is true.

**Inductive step:**

Let's assume the statement holds for n = k :

$$
\overline{\bigcap_{i=1}^{k} A_i} = \bigcup_{i=1}^{k} \overline{A_i}
$$

For n = k+1:

$$
\overline{\bigcap_{i=1}^{k+1} A_i}
= \overline{\left(\bigcap_{i=1}^{k} A_i\right) \cap A_{k+1}}
$$

Using De Morgan’s Law:

$$
= \overline{\bigcap_{i=1}^{k} A_i} \cup \overline{A_{k+1}}
$$

Then using inductive hypothesis:

$$
= \left(\bigcup_{i=1}^{k} \overline{A_i}\right) \cup \overline{A_{k+1}}
= \bigcup_{i=1}^{k+1} \overline{A_i}
$$

Therefore, the statement holds for all $n \in \mathbb{N}$. 