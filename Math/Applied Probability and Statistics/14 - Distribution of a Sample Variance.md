---
title: Distribution of a Sample Variance
draft: false
tags:
  - Mathematics
---

Distribution of Sample Varience
$$
S^2 = \frac{1}{n-1} \sum ^n_{i=1} (X_i - \bar{X})^2
$$

It turns out that the quantity 

$$
\chi^2 = \frac{1}{\sigma_x^2}\sum^n_{i=1}(X_i-\bar{X})^2
$$

is *Chi-squared* distributed with V = N-1 degrees of freedom 

![[PXL_20241029_114139024.jpg]]

So consider 

$$
S^2 = \frac{1}{n-1} \sum ^n_{i=1} (X_i - \bar{X})^2
$$

$$
\chi^2 = \frac{1}{\sigma_x^2}\sum^n_{i=1}(X_i-\bar{X})^2 = \frac{S^2(n-1)}{\sigma_x ^2}
$$

Where sigma follows a chi squared distribution with $\nu =n -1$ degrees of freedom.

So, we can now compute things like this 

$$
P(S^2_x > 2\sigma_x^2) = \frac{S^2(n-1)}{\sigma_x ^2} > 2(n-1)
$$
### Chapter 6 Parameter Estimation (Confidence Intervals)

Point Estimates: 
$$
\bar{x} =\frac{1}{n}\sum x_i
$$
$$
S^2 = \frac{1}{n-1} \sum_{i=1}^n (X_1)^2
$$

<u>Confidence Intervals</u>

We want to come up with two numbers, L and U, such that $P(L \leq \mu_x \leq u) = 1 - \alpha$, where $1 - \alpha$ is the confidence, and $\alpha$ is the significance. 

![[PXL_20241029_120334324.jpg]]

So choose $\alpha$ to be small, (but not too small)
- If $\alpha$ = 0, I'm 100% confident that {L,U} enclose the true mean, $\mu_x$ 
	- We would need $[L, U]$ = $[-\infty, +\infty$]
	- Usually, $\alpha =0.05$ to $0.10$ is selected

How do we find L and U? 

Consider 
$$
P(-Z_{\frac{\alpha}{2}} < \frac{\bar{X} - \mu_x}{\sigma_x / \sqrt{n}})
$$

There is a proof to say that

$$
[L,U]_{1- \sigma} = \bar{X} \pm Z_{\frac{\alpha}{2}} \frac{\sigma_x}{\sqrt{n}}
$$

![[PXL_20241029_121904954.jpg]]

If we are finding a confidence interval on $\mu_x$ then, 
$$
(L,U) = (\space \space \bar{X} \space \space) \pm (Z_{\frac{\alpha}{2}} \space \underline  {\text{or}} \space t_{\frac{\alpha}{2}}, v)(\sigma_{\bar{X}})
$$

If we are finding a confidence interval on $\mu_x1, -\mu_x2$ where $\sigma_x1$ and $\sigma_x2$ are <font color="#c0504d">known</font>, then 

![[PXL_20241029_122425961.jpg]]

We sometimes want to just know a <font color="#c0504d">one-sided</font> confidence bound, i,e L or U individually:

![[PXL_20241029_122624277.jpg]]

--- 
### Example 1 

![[PXL_20241029_123402552.jpg]]

### Example 2 

![[Pasted image 20241029093630.png]]

We are told $\bar{X} =960$, $n=25$, $\sigma_x^2 = 225 \space \space (\sigma_x = 15)$ 
(sigma is known, use Z)

$$
(L,U) = (\space \space \bar{X} \space \space) \pm (Z_{\frac{\alpha}{2}}) (\sigma_{\bar{X}})
$$

$$
(L,U) = (\space \space \bar{X} \space \space) \pm Z_{\frac{\alpha}{2}} (\frac{\sigma_{\bar{X}}}{\sqrt{u}})
$$

$$
(L,U) = (960) \pm Z_{0.025} (\frac{15}{\sqrt{25}})
$$

$$
(L,U) = (960) \pm (1.960) (\frac{15}{\sqrt{25}})
$$

$$
= [954.1, 965.9]
$$

We are 95% confident that the true $\mu_x$ is in this interval. 

---
