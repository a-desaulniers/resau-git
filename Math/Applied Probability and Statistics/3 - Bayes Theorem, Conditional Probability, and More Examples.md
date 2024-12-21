---
title: Bayes Theorem, Conditional Probability, and More Examples
draft: false
tags:
  - Mathematics
---
Recall that 

$$ 
P(A\cup B) = P(A) +P(B) - P(A\cap B)
$$

*And watch out for the disjoint case!* 

---
### Example 1

![[Pasted image 20240912084404.png|500]]

---

### Example 2

Here, is a very common two group problem. Defectives and Non - Defectives

![[Pasted image 20240912085734.png|500]]


"55 Choose Two", this is a [[2 - Combinations and Permutations#^8b383e|combination]] , because we don't care about order. 

---

### Example 3

![[Pasted image 20240912091030.png]]


You could do the math, or since we already know the chances of non being defective, you could just find the other cases (in this case, 1 - (99/118) )

---

### Example 4

![[Pasted image 20240912092014.png]]


---

### Conditional Probability 

We say that the probability of A <font color="#c0504d">given</font> that B has occurred is

$$
P(A|B)  = \text {Conditional Probability }
$$
| = Given 

On the left of the given, it states the new probability rules to apply
On the right of the given, you receive information of what happened previously.

![[PXL_20240912_124842395.jpg]]

$P(A\cap B = P(A|B)P(B)$

We also have:

$P(B\cap A) = P(B|A)P(A)$

...

And a bit more math, and we get [[Class 5 - Total Probability Theorem, and Event Trees#Bayes Theorem|Bayes' Theorem]] (***Very famous, and important***)

$$
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
$$
