---
title: Hypothesis Tests
draft: false
tags:
  - Mathematics
---
**Chapter 7**

#### Hypothesis Tests:

A test of competing hypothesis. 
- $H_o$ : Null hypothesis
	- Default conditions
	- <font color="#c0504d">Can never be proved</font>. The test can never prove the null
- $H_a$ : Alternative Hypothesis
	- What you are trying to prove

####  Examples:
1) Legal Justice System; Innocent until proven guilty (Innocent = $H_O$), (Guilty = $H_a$).
	- If the evidence in *far enough* away from innocence, you are *proven* to be guilty at some level of confidence. Here, if you make a mistake in your alternative hypothesis, somebody goes to jail innocently 

2) The Scientific Method
	- $H_o$ = Current Theory (say the theory of general relativity right now). 
	- $H_a$ = Your new theory
		- So you gather data, and if it sufficiently supports your theory, (i.e, far enough away from $H_o$ in the direction of $H_a$) 

---
##### Example 1 

Note: The equality must always be on $H_o$. We test $\mu_x = 10$ (hardest to reject, and gives us default mean)

![[PXL_20241107_125748039~2.jpg]]
![[PXL_20241107_130157307.jpg]]

If so, we reject $H_o$ and conclude, with at least ($1 - \alpha$) confidence, that $H_a$ is correct.

**Note:** This is a one-sided test. (when we have a less than, or greater than $H_a$). We'd use $Z_{\alpha}$ or $T_{\alpha}$

---
##### Example 2 (Two sided test this time)

(Two sided. So we use $Z_{\frac{{\alpha}}{2}} )$ 

![[PXL_20241107_131331540.jpg]]

---
#### Types of Errors

- Type 1: Rejecting $H_o$ when it is true
	- P\[Type 1 Error] = $\alpha$ 
		- We choose this so choose $\alpha$ to be small, but not too small. $\alpha$ of 0.05 or 0.10 is selected

- Type 2: Failing to reject $H_o$ when it is *false* 
	- Problem: If $H_o$ is false, we do not know what $\mu_x$ is. Our $H_o$ tells us the mean by default, so that being wrong is a big problem
		- P\[Type 2 Error] = $\beta$  $\leftarrow$ (*harder to computer*, so we'll basically ignore this)
			- This increases as $\alpha$ decreases (again, why we don't want to choose $\alpha$ too small)

---
#### P - Value 

This is the value of $\alpha$ at the boundary of rejecting $H_o$ 

= The probability of observing a future test statistic at least as extreme as the one observed <font color="#c0504d">in the direction of $H_a$ </font>

---
#### Example

Suppose
$H_o$ : $\mu_x =$ 0
$H_o$ : $\mu_x \neq$ 20

and we have computed a test statistic 

$$
Z = \frac{()-()}{()} = 2.6
$$
(*this means that our* $\bar{X}$ *is 2.6 standard deviations away from $H_o$ : $\mu_x =$ 20)

P-value (i.e. = $P[Z>2.6 \cup Z< -2.6]$ = 2($1-\phi(2.6))$ 

Small P-values support $H_a \rightarrow$ suggests that $H_o$ is false, and should be rejected. If $\alpha$ is selected to be greater than the P-value, we reject $H_o$ 

Large P-Values support $H_o$

---
