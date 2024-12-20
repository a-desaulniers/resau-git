---
title: Continuous Distributions
draft: false
tags:
  - Mathematics
---
A continuation of Bernoulli Trials!

**Exponential Distribution** (This is our first <font color="#c0504d">continuous</font> distribution)

Let T<sub>1</sub> = time until the next "success”

Distribution? CDF:
$$
P[T_1 < t] = P[N_t \geq t]
$$
$$
F_{T1}(t)= P(T_1 < t) = 1 - P(N_t =0)
$$

>[!note] Exponential Distribution
>There is a proof to say
>
>[[Summary of Statistics Distributions#3. Exponential Distribution|Exponential Distribution]]
>

A reminder of the standard deviation (**σ**_<sub>T1</sub>) 
$$
σ= \frac{1}{\lambda}
$$
Because variance is that with a lambda squared!


--- 

**Gamma Distribution** (analogous to the [[9 - Distributions Continued#^8a4631|negative binomial]])

Let T<sub>k</sub> = Time to the K<sup>th</sup> success

>[!note] Gamma Distribution
>There is a proof to say, that 
>
>[[Summary of Statistics Distributions#4. Gamma Distribution|Gamma Distribution]]
>
>As before, PMF is integrated PDF

![[PXL_20241008_122143583.jpg]]

Looking at the CDF (Big F function), we can see that the higher the K value we have, and more T<sub>1</sub> terms we are going to have stretching out the function. 

This is another interpretation of, let's call it T<sub>3</sub>, or the span of the whole time period. T<sub>1</sub> being the time in between each time period. 

---
**Memoryless Property**

- Since every trial is independent of all other trials, the past is forgotten

---

### Other Continuous Distributions 

**Weibull Distribution**

- The Weibull distribution is a generalization on the exponential distribution 
- It is a very common lifetime model distribution, or “time to failure” of a system

>[!note] Weibull Distribution
>There is a proof to say
>
>[[Summary of Statistics Distributions#9. Weibull Distribution|Weibull Distribution]]

If B = 1 for big F(x), you've got an exponential, and a **constant failure rate**
If B < 1 for big F(X), you tend to get more failures early on, and fewers failures later on
	- This is known as an improving system, eg, A.I, bacteria colony, red wine, glue, concrete (until it starts to fail, but initially, it takes time to set)
If B > 1 for big F(X), you've got a degrading system. This is much more common. 

![[PXL_20241008_124757391.jpg]]
