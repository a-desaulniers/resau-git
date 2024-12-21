---
title: Independence vs Disjunction
draft: false
tags:
  - Mathematics
---
### Independence 

If events A and B are *independent*, then the occurrence of one does not effect the probability of occurrence of the other. 

*I.e* 
$$
P(A|B) = P(A)
$$
If A and B are independent. 

Just because B happened, doesn't make A any more likely.

This means that
$$
P(A\cap B) = P(A)P(B)
$$

P(A)P(B) (the product of the two probabilities) is much simpler to calculate!

![[Pasted image 20241019124521.png]]

- If these are true, A and B are **independent**
- If these are false, A and B are **dependent**

> [!note] 
> "*independent* and "*disjoint*" are <u>opposites</u>
>
> If A and B are *disjoint* then
> $P(A\cap B) = 0 \neq P(A)$
> 
>If Independent, A and B must overlap by a specific amount
>
>Any time you see a probability of an intersection, you should ask "*are those independent?*" 
>
>Consider
>$P(A\cap B\cap C) = P(A|B \cap C)P(B|C)P(C)$
>
>$$
>= P(A)P(B)P(C) \space\space \text{if independent}
>$$
>
>![[PXL_20240917_123025728.jpg]]

<u>So the rules!</u>

P(**Union**) ← Are they *disjoint*? 

P(**Intersection**) ← Are they *independent*?

---
### Example 1

![[PXL_20240917_123935942.jpg]]

Here, the machines being independent ***saves us a lot of time!***

---

