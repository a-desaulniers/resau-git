---
title: Sampling Distributions
draft: false
tags:
  - Mathematics
---
### Chapter 5: Sampling Distribution

**Definition Sheet:**

- **Population**
	- Collection of all possible outcomes of our experiment 
- **Sample**
	- Collection of observations from the population
	- X<sub>1</sub>, X<sub>2</sub>, … X<sub>n</sub>
	
- **Random Sample**
	- A set of independent observations

- **Statistic**
	- A function of one or more random variables

Statistics will be concerned with

- **Sample Mean**
	- $$
	\overline{X} = \frac{1}{n}\sum^n_{i-1}X_i
	$$
- Sample Variance
	- $$
	 S^2 = \frac{1}{n-1}\sum(X_i - \overline{X})
	$$

Sample mean and Sample Variance are random before we take our observations…

After we've taken our random sample, we know X<sub>1</sub>, X<sub>2</sub>, … X<sub>n</sub>, and we get

- $$
	\overline{X} = \frac{1}{n}\sum^n_{i-1}X_i
	$$
	Which is a realization of x̄

and 

- $$
	 S^2 = \frac{1}{n-1}\sum(X_i - \overline{X})
	$$
	Which is a realization of S<sup>2</sup>





> [!tip] One other little note...
> X<sub>i</sub> has a sample mean as well, but would be quite a bit harder to find. If you were calculating height of a series of students for example, the sample mean of the group of students would be x̄ for example. 
>
>However, this isn't representative of EVERY student on the planet, or the ENTIRE Population. You would need to find the sample mean (μ) of X<sub>i</sub> for that.

If I repeat the process, and observe another set of observations, I'll get a new X<sub>1</sub>, X<sub>2</sub>, … X<sub>n</sub>, and a new x̄ and S<sup>2</sup>

--- 
### Example One

![[Pasted image 20241017085845.png]]

μ<sub>x</sub> = E(x<sub>i</sub>) 100Ω
σ = 10Ω
N = 25
We know this is a Random Distribution (*follows a normal distribution*)
Let X<sub>i</sub> = X of I resistor

![[PXL_20241017_120650078.jpg]]
![[PXL_20241017_121236326.jpg]]

$$
\therefore P(\overline{X}<95) = P(Z_1 < \frac{95 -\mu_\overline{X}}{\sigma_\overline{X}} = P(Z < \frac{95 -\mu_{X}}{\frac{\sigma_x}{\sqrt{n}}}) =1-\Phi(2.5) = 1 - 0.99379 =\underline{0.00621}
$$

Remember, Φ is pulled from a lookup table. 

---
### Example Two

![[Pasted image 20241017092111.png]]

μ<sub>x</sub> = E(x<sub>i</sub>) 1.01
σ = 0.003
N = 9 (Here, we have to assume "Random Samples”. Otherwise, this isn't doable.)
We know this is a Random Distribution (*follows a normal distribution*)

We want to find:

P((x̄ < 1.009) U (x̄ > 1.011))

Distribution? We need; μ<sub>x̄</sub> and σ<sub>x̄</sub> 

μ<sub>x̄</sub> = μ<sub>x</sub>,  σ<sub>x̄</sub> = σ<sub>x</sub>/sqrt{n} 

Here, we'll find the probability for one half of the curve, and then double it (because they are the same thing on each side)

![[PXL_20241017_122915498.jpg]]

---
Now, what happens if I don't know σ<sub>x</sub>?

We must now estimate σ<sub>x</sub> with S<sub>x</sub>

where S<sub>x</sub><sup>2</sup> =

$$
	 S^2_x = \frac{1}{n-1}\sum(X_i - \overline{X})^2
	$$
So, our standardization now becomes:

![[PXL_20241017_123411043.jpg]]




