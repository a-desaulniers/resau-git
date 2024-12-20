---
title: Confidence Intervals on Proportions
draft: false
tags:
  - Mathematics
---
Proportions = Probability of "success" in Bernoulli

We want to estimate P

$$
\hat{P} = \frac{\text{number} \space \text{of} \space \text{"successes"} \space}{\text{number} \space \text{of} \space \text{trials} \space} = \frac{N_n}{n}
$$
Confidence Interval on P

$$
[L,U]_{1-\alpha} = (\hat{P}) \pm (Z_{\frac{\alpha}{2}})(\sigma_{\hat{p}})
$$

This is a two-sided confidence interval

Where $\sigma_{\hat{P}}^2 = Var(\hat{P}) = Var(\frac{N_n}{n}) = \frac{1}{n^2}Var(N_n) = \frac{npq}{n^2} = \frac{pq}{n} \approx \frac{\hat{p} \hat{q}}{n}$

(Note: In hypothesis tests, we use the assumed p (under H<sub>o</sub>))

$$
(L,U)_{1-\alpha} = (\hat{P}) \pm (Z_\frac{\alpha}{2})\sqrt{\frac{\hat{p} \hat{q}}{n}}
$$
$$
\hat{q} = 1 - \hat{P}
$$


Note, if this interval includes negative numbers, or numbers above 1.0, then our approximation is *bad*. 

Rule of thumb, if $n\hat{p} \geq 5$ or $n\hat{q} \geq 5$, you've got a problem. Your data will be centred too close to zero, and there will be negative numbers present.

---
