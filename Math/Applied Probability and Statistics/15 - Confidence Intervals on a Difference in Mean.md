---
title: Confidence Intervals on a Difference in Mean
draft: false
tags:
  - Mathematics
---

##### Three Cases
1) Where $\sigma_{x_1}$ and $\sigma_{x_2}$ are known 
$$
[L,U)_{1- \alpha} = (\bar{x}_1 - \bar{x}_2) \pm (Z_{\frac{\alpha}{2}})(\sigma_{\bar{x}_1 - \bar{x}_2})
$$

where $(\sigma_{\bar{x}_1 - \bar{x}_2}^2)$ = Var($\bar{x}_1 - \bar{x}_2$) = $\text{Var}(\bar{x}_1) + \text{Var}(\bar{x}_2)$.

![[PXL_20241031_114928939.jpg]]

2) $\sigma_{x_1}$ and $\sigma_{x_2}$ are<font color="#c0504d"> unknown</font> (*we will use $t_{\frac{\alpha}{2}})$ 
	- If we have n<sub>1</sub> and n<sub>2</sub>, what is V? (see notes for expression for V)
	- Simplifying assumption that  $\sigma_{x_1}$ =  $\sigma_{x_2}$ =  $\sigma_{x}$ (unknown), we get an improved estimate of  $\sigma_{x}$ by <font color="#c0504d">pooling</font> the data 
	
$$
S_p^2 = \frac{(n_1 - 1)S_1^2 + (n_2 - 1)S_2^2}{(n_1 + n_2 -2)}
$$

	- This is the weighted average of S<sub>1</sub><sup>2</sup> and S<sub>2</sub><sup>2</sup>
	
	Where 
$$
S_1^2 = \frac{1}{n_1 - 1} \sum ^{n_1}_{i =1}(X_{1_i} - \bar{x}_1)^2
$$

	and 
$$
S_2^2 = \frac{1}{n_2 - 1} \sum ^{n_2}_{i =1}(X_{2_i} - \bar{x}_2)^2
$$

	If $u_1$ = $n_2$, then Sp<sup>2</sup> = $S_p^2 = \frac{(n_1 - 1)S_1^2 + (n_2 - 1)S_2^2}{(2(n-1)}$ = $\frac{1}{2}(S_1^2 + S_2^2)$
	
	Now $\nu$ = n<sub>1</sub> + n<sub>2</sub> -2 
	
![[PXL_20241031_120320826.jpg]]
	
	
3) Paired Data

![[PXL_20241031_120659635.jpg]]

Solution: Take differences: Let D<sub>i</sub> = $X_{1_i} - X_{2_i}$, & d<sub>i</sub> = $x_{1_i} - x_{2_i}$

Now compute 
$$
\bar{d} = \frac{1}{n}\sum^n_{i=1}d_i
$$
Where $\bar{d}$ is an estimate of $\mu_D = \mu_{1_i} - \mu_{2_i}$. We will also need $S_d^2 = \frac{1}{n-1}\sum^n_{i=1}(d_i-\bar{d})^2$

Now, 

$$
[L,U)_{1-\alpha} = ( \bar{d} \pm (t_{\frac{\alpha}{2},n-1})\frac{S_d}{\sqrt{n}}
$$

---

In order for two pieces of data to be paired, they must have some sort of correlation. 
