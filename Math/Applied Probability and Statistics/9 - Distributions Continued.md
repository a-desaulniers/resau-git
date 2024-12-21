---
title: Distributions Continued
draft: false
tags:
  - Mathematics
---
##### Geometric Series, Cont'd 

> [!note] A reminder about Geometric Series
>
>Let T<sub>1</sub> = Number of trials until the first (or next) "*success*"
>
>Distribution? 
>
>P(T<sub>1</sub> = K)   = <font color="#c0504d">?</font>,   K = 1,2,... , ∞
>
>![[PXL_20241001_125800524.jpg]]
>
>$$
>P(T_1 = k) = pq^{k-1}, k = 1,2,.. , ∞
>$$

To make this easier, the expected value is just.

$$
E(T_1) =\frac{1}{p}
$$
When is the expected next time that something will happen given the probability?

For variance, it's a little bit more non-sensible. 

$$
Var(T_1) = \frac{8}{p^2}
$$

---
## Example One

![[Pasted image 20241003084927.png]]

- How shall we model this? 

Let's assume each year is a trial, and each trial will have a a max wind which either exceeds, or doesn't the "50-year windspeed" (E(T<sub>1</sub>) = 50)

Let X<sub>i</sub> be 1 if our windspeed exceeds the 50 year value, and 0 if it does not. 

$$ 
P = P(x_i = 1) = \frac{1}{50} = \frac{1}{E(T_1)} = 0.02
$$

> [!note] Note
> Often times, you'll be given an expected time, and not directly a probability. You'll just have to flip it like I did above.

*A*) We want P(T<sub>1</sub> = 5)  <u>(F, F, F, F, S)</u>
$$
P(T_1 = 5) = pq^{5-1} = pq^4 = (0.02)(0.98)^4 = \underline{0.018}
$$

*B*) We want P(N<sub>5</sub> ≥ 1 ) = P(T<sub>1</sub> ≤ 5 )  <u>(F,S,F,F,F)</u>

![[PXL_20241003_115925284.jpg]]

---
> [!note] Negative Binomial 
>
>Let T<sub>k</sub> = Number of trials until the k<sup>th</sup> "success"
>
>Distribution? 
>
>P(T<sub>k</sub> = m)   = <font color="#c0504d">?</font>,   M = k, k+1,... , ∞
>$$
>P[T_k = m] = {m-1 \choose k-1} p^kq^{m-k}, m = k, k+1,...
>$$
>This is pretty similar to Geometric! If `K =1`, then it really is the same. It's a generalization.
>
>![[PXL_20241003_120928154.jpg]]
>
>---
>M = Number of Trials
>K  = Number of Successes in M Trials

^8a4631

And the variance of T<sub>k</sub> is

$$
Var(T_k) = Var (T_{11}+ T_{12} + ... + T_{1k}) = Var(T_{11}) + Var(T_{12}) ..
$$
$$
Var(T_k) = \frac{q}{p^2} + \frac{q}{p^2} + ... =\frac{kq}{p^2}
$$
And the expected value is 
$$
E(T_k) = E(T_11) + E(T_12) + ... + E(T_1k)
$$

$$
E(T_k) = \frac{1}{p} + \frac{1}{p} + ... + \frac{1}{p} = \frac{k}{p}
$$


---

### Example Two

In the transmission tower problem from above, what is the probability that the second 50 year wind will occur in the 5th year of service?

We want P(T<sub>2</sub> = 5)

$$
P(T_2 = 5) = {4 \choose 1} p^2q^3
$$
$$
P(T_2 = 5) = {4 \choose 1} (0.02)^2(0.98)^3 = \underline{0.0015}
$$
---

**Now, let's do something fun.**
##### The Rate of Success, Poisson Distributions

Lets let every instant in time become a Bernoulli Trial. Now, "successes" can occur at any instant 

![[Pasted image 20241003092437.png]]

Problems: Let N<sub>n</sub> equal the number of "successes" in time t (?)
N > ∞ on any time interval

$$
E(N_n) = np \rightarrow \infty \space \text{unless}\space p \rightarrow 0
$$

If P > 0
![[Pasted image 20241003092748.png]]


We need to replace P with a mean <font color="#c0504d">rate</font> of "successes", 
<font color="#c0504d">λ</font> (number per unit time)

Let N<sub>t</sub> = Number of "successes" in time T (<font color="#c0504d">discrete</font>)

>[!note] Poisson Distribution
>$$
>P(N_t = k) = \frac{(\lambda t)^k}{k!}e^{-\lambda t}, t\geq 0
>$$


> This is the analog to the [[8 - Common Distributions and Bernoulli Trials#^486839|binomial distribution]] (N<sub>n</sub> = number of successes )

<u>and of course</u>...

Expected Value

$$
E(N_t) = λt
$$
Variance 

$$
Var(N_t) = \lambda t \rightarrow \sqrt{\lambda t}
$$

---

[[Summary of Statistics Distributions]]