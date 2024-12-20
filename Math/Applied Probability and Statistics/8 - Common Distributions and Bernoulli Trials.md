---
title: Common Distributions and Bernoulli Trials
draft: false
tags:
  - Mathematics
---
## Chapter 4: Common Distributions

### Discrete Distributions 

**Bernoulli Trials**:
- A sequence of trials each having
	1) Two possible outcomes
	2) Constant probability of "success"
	3) Trials are independent

In the theory of probability and statistics, a Bernoulli trial is a random experiment with exactly two possible outcomes, "success" and "failure", in which the probability of success is the same every time the experiment is conducted.

An example of this would be a **coin toss**, the probability doesn't change each flip!

Let's define an X<sub>i</sub> here:

X<sub>i</sub> = 1, if the i<sup>th</sup> trial is a "success"
X<sub>i</sub> = 0, if the i<sup>th</sup> trial is a "failure"

and let 

P(X<sub>i</sub> = 1) = **p**
P(X<sub>i</sub> = 0) = 1 - p = **q**

🡹 This here, is a [[6 - Random Variables, and the CDF#^c94bca|Probability Mass Function (PMF)]] 

![[PXL_20241001_120803816.jpg]]

Where E(X<sub>i</sub><sup>2</sup>)  = (1)<sup>2</sup>p = p(1 - p) = **pq**

This leads to distributions:

> [!note] Binomial Distributions
>$$
>\text{Let} \space N_n = \sum_{i=1}^n X_i = (0+1+1+0+1+0+0..)
>$$
>*i.e equalling*
>
>= number of "successes" in *n* trials.

^486839


![[PXL_20241001_121921399.jpg]]

= p<sup>2</sup>q<sup>2</sup> +  p<sup>2</sup>q<sup>2</sup> + ...

= (Four choose Two "4 over 2") * p<sup>2</sup>+q<sup>2</sup>

> [!tip] General Formula for distributions
>
>$$
>P(N_n = k) = {n \choose k} \space p^kq^{n-k} , \text{for}\space k = 1,2,3...n)
>$$


![[PXL_20241001_122721211.jpg]]

**Varience for Bernoulli Trials** 

$$
Var[\sum_{i=1}^n X_i] = \text{Sum}\space \text{of}\space  \text{variances}\space \text{since}\space  \text{assumed}\space \text{independent.}
$$

$$
Var[\sum_{i=1}^n X_i] = (pq + pq + pq + ... + pq)
$$
since X<sub>i</sub> = pq

$$
= npq
$$
##### Example 1 

![[Pasted image 20241001093725.png]]

![[PXL_20241001_123642573.jpg]]

##### Example 2

![[Pasted image 20241001093909.png]]

This is a sequence of Bernoulli Trials. Because of this, we can assume independence. Without that piece, this is not solvable. 

N<sup>10</sup> = Number of failures in N trials

We want to find

$$
P[N_{10} \geq 2 |N_{10} \geq 1]
$$

> [!note] Recall That...
>
>$$
>P(A|B) = \frac{P(A\cap B)}{P(B)}
>$$

So...
$$
P[N_{10} \geq 2 |N_{10} \geq 1] = \frac{P[N_{10} \geq 2 \cap N_{10} \geq 1]}{P(N_{10} \geq 1)}
$$
$$
\frac{P[N_{10} \geq 2]}{P(N_{10} \geq 1)}
$$

Worked out that is...

![[PXL_20241001_125101581.jpg]]


> [!note] Geometric Distribution
>
>Let T<sub>1</sub> = Number of trials until the first (or next) "*success*"
>
>Distribution? 
>
>P(T<sub>1</sub> = K)   = ?,   K = 1,2,... , ∞
>
>![[PXL_20241001_125800524.jpg]]
>
>$$
>P(T_1 = k) = pq^{k-1}, k = 1,2,.. , ∞
>$$

---

[[Summary of Statistics Distributions]]


