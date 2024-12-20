---
title: Random Variables Continued
draft: false
tags:
  - Mathematics
---
### Main Descriptors

- Mean: **μ**
	- Balance point, or the first moment

$$
\int^{\infty}_{\infty} f_x(x)dx
$$
$$
f_x(x) = P(X=x)
$$
- Median: x͂
	- Point which divides the distribution in half
	- If the distribution is symmetric about the mean, then x͂ = **μ**<sub>x</sub>
	
![[PXL_20240926_114240028.jpg|575]]

- Mode
	- Most common, or likely point. Usually the highest point on one of these PDF graphs.

---

### Expectation Operator

$$
E(\text{ANYTHING}) = \sum_{\text{all}\space \text{things}}(anything)\times P(\text{ANYTHING}=\text{anything})
$$
When I say anything, I really mean any function of X

![[PXL_20240926_115027205.jpg|450]]

- E(X) = Sum of all x's times their probability of occurrence

- E(sum) = Sum of Expectations

**What about the expectation of a constant times X?** E(ax)
$$
\int^{\infty}_{\infty} f_x(ax)dx
$$
$$
a\int^{\infty}_{\infty} f_x(x)dx
$$
$$
aE(X)
$$
**What about the expectation of a constant, just normally?**
$$
E(A) = A
$$
- I mean, the number isn't random anymore. The expectation of two... would just be two you'd hope, right? 

**What about the expectation of a constant, plus a constant times X?*

$$
E(a+bX) = E(a)+ E(bX) = a + bE(X)
$$

---
### Measures of Variability 

**σ** = Standard Deviation
**σ**<sup>2</sup> = Varience

There is a proof to say:

$$
Var(X) = E(x^2) - E^2(X)
$$
$$
E(X^2) = Var(X) + E^2(X)
$$

You can tough it out through that integral, or you can use the formula


### Covarience

Now, let's think about two random variables, X and Y

![[PXL_20240926_121008579.jpg|450]]

- Here, there seems to be a **linear** dependence between X and Y

![[PXL_20240926_121147501.jpg|450]]

- Here, there doesn't seem to be any dependence at all in between X and Y. Just completely random.

![[PXL_20240926_121350681.jpg]]

- In this case, we have **non linear dependence**. There's no linear dependence here! If we draw our line of best fit, there's a pretty telling sign here that we have no linear dependence. 

![[PXL_20240926_121636145.jpg]]

- So, Cov(X,Y) has the same sign as the slope.

**There is a proof to say,** 

$$
Cov(x,y) = E(XY) - E(X)E(Y
$$
$$
E(XY) = Cov(x,y) + E(X)E(Y)
$$

The E(XY) term is not trivial to find, and is usually either given, or solved for using the covariance. 


Another point, if the Covariance is completely linearly dependent, like Y = X for example,

$$
Cov(X,Y) = E(XY) - E(X)E(Y) = E(X^2) - E^(X) = \text{Varience}
$$

So if the Covariance is completely linearly dependent, it is **directly equal** to Varience

---
### Correlation Coefficient

$$
\text{Correlation} \space  \text{Coefficient}= ρ_{xy} = \frac{\text{Cov}(x,y)}{(σ_X)(σ_Y)}
$$


If X and Y are uncorrelated (Cov(XY) = 0), or independent (Cov(X,Y) = 0) and no other dependence

$$
Cov(X,Y) = E(XY) - E(X)E(Y) = 0
$$
$$
E(XY) = E(X)E(Y)
$$
---
### Linear Combinations
(or just a fancy way to say sum)

So typically in engineering, we have a total load capacity made up of smaller loads.

Say Y = X<sub>1</sub> + X<sub>2</sub>

If I know about X<sub>1</sub> and X<sub>2</sub>, what is the mean and variance of Y?

$$
\text{Mean}, \space μ_y = E(Y) = E(X_1 + X_2) = E(X_1) + E(X_2) = μ_{x1} + μ_{x2}
$$

Variance is a little more complicated…

*There is a proof to show that….* 

We get that 

$$
\text{Var(sum)} \space = \text{sum}\space \text{of}\space \text{all}\space \text{the}\space \text{possible}\space \text{covariances.}
$$

For example
$$
Var(Y) = Var(X_1 + X_2) = Var(X_1) + 2Cov(X_1,X_2) + Var(X_2)
$$


The general rule is 
$$
\sum_{i=1}^n \sum_{j=1}^n a_ia_jCov(X_i,X_j)
$$


![[PXL_20240926_125127411.jpg]]


