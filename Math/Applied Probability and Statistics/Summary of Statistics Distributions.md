---
title: Summary of Statistics Distributions
draft: false
tags:
  - Mathematics
---
# Summary of Discrete Statistics Distributions

## 1. Bernoulli Distribution

- **Description**: A distribution for a single trial with two possible outcomes (success or failure).
- **Probability Mass Function (PMF)**:
  $$
  P(X = x) = 
  \begin{cases} 
  p & \text{if } x = 1 \\
  1 - p & \text{if } x = 0
  \end{cases}
  $$
- **Parameters**: $( p \in [0, 1] )$ (success probability)
- **Mean**: $( \mu = p )$
- **Variance**: $( \sigma^2 = p(1-p) )$

---

## 2. Binomial Distribution

- **Description**: The number of successes in \( n \) independent Bernoulli trials.
- **PMF**:
  $$
  P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}, \, k = 0, 1, \dots, n
  $$
- **Parameters**: $( n \in \mathbb{N} )$ (number of trials), $( p \in [0, 1] )$ (success probability)
- **Mean (Expected Value)**: $( \mu = np )$
- **Variance**: $( \sigma^2 = np(1-p) )$

---

## 3. Geometric Distribution

- **Description**: The number of trials until the first success.
- **PMF**:
  $$
  P(X = k) = (1-p)^{k-1} p, \, k = 1, 2, \dots
  $$
- **Parameters**: $( p \in [0, 1] )$ (success probability)
- **Mean (Expected Value)**: $( \mu = \frac{1}{p} )$
- **Variance**: $( \sigma^2 = \frac{1-p}{p^2} )$

---

## 4. Negative Binomial Distribution

- **Description**: The number of trials until the $( r )$-th success.
- **PMF**:
  $$
  P(T_k = m) = \binom{m-1}{k-1} p^k (1-p)^{m-k}, \text{ for } m\geq k
  $$
- **Parameters**: $( k \in \mathbb{N} )$ (number of successes), $( p \in [0, 1] )$
- **Mean (Expected Value)**: $( \mu = \frac{k}{p} )$
- **Variance**: $( \sigma^2 = \frac{k(1-p)}{p^2} )$

---

## 5. Poisson Distribution

- **Description**: Models the number of events occurring in a fixed interval of time/space.
- **PMF**:
  $$
  P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}, \, k = 0, 1, 2, \dots
  $$
- **Parameters**: $( \lambda > 0 )$ (average rate of occurrence)
- **Mean (Expected Value)**: $( mu = \lambda t )$
- **Variance**: $( \sigma^2 = \lambda t )$

---

# Summary of Continuous Statistics Distributions

## 1. Uniform Distribution

- **Description**: All intervals of the same length in the range \([a, b]\) are equally likely.
- **Probability Density Function (PDF)**:
  $$
  f(x) = 
  \begin{cases}
  \frac{1}{b-a}, & a \leq x \leq b \\
  0, & \text{otherwise}
  \end{cases}
  $$
- **Parameters**: $( a, b \in \mathbb{R})$, $( a < b )$
- **Mean (Expected Value)**: $( \mu = \frac{a + b}{2} )$
- **Variance**: $( \sigma^2 = \frac{(b-a)^2}{12} )$

---

## 2. Normal (Gaussian) Distribution

- **Description**: The bell-shaped curve, symmetric around the mean. This one is ugly, and you'll be using the Z- Tables instead of this… hopefully.

- **PDF**:
  $$
  f(x) = \frac{1}{\sqrt{2 \pi \sigma^2}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right), \, x \in \mathbb{R}
  $$
- **Parameters**: $( \mu \in \mathbb{R} )$ (mean), $( \sigma > 0 )$ (standard deviation)
- **Mean (Expected Value)**: $( \mu)$
- **Variance**: $( \sigma^2)$

---

## 3. Exponential Distribution

- **Description**: Models the time between independent events occurring at a constant rate.
- **PDF**:
  $$
  f(x) = 
  \begin{cases}
  \lambda e^{-\lambda x}, & x \geq 0 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- **Parameters**: $( \lambda > 0 )$ (rate parameter)
- **Mean (Expected Value)**: $( \mu = \frac{1}{\lambda} )$
- **Variance**: $( \sigma^2 = \frac{1}{\lambda^2} )$

---

## 4. Gamma Distribution

- **Description**: Generalizes the Exponential distribution; models waiting time for \( k \) events.
- **PDF**:
  $$
  f(x) = 
  \begin{cases}
  \frac{\lambda}{(k-1)!}(\lambda t)^{k-1} e^{-\lambda x} \\
  0, & \text{otherwise}
  \end{cases}
  $$
-  **PMF**
$$
F(t) = 1 -e^{-\lambda t} \sum^{k-1}_{j!}\frac{(\lambda t)^j}{j!} \space\text{  if } k \text{ is a positive integer, and } t \geq 0
$$

- **Parameters**:
  - $( k > 0 )$: Shape parameter
  - $( \lambda > 0 )$: Rate parameter
- **Mean (Expected Value)**: $( \mu = \frac{k}{\lambda})$
- **Variance**: $( \sigma^2 = \frac{k}{\lambda^2} )$

---

## 5. Beta Distribution

- **Description**: Models proportions or probabilities in the interval \([0, 1]\).
- **PDF**:
  $$
  f(x) = 
  \begin{cases}
  \frac{x^{\alpha-1} (1-x)^{\beta-1}}{B(\alpha, \beta)}, & 0 \leq x \leq 1 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- **Parameters**: $( \alpha, \beta > 0 )$
- **Mean (Expected Value)**: $( \mu = \frac{\alpha}{\alpha + \beta} )$
- **Variance**: $( \sigma^2 = \frac{\alpha \beta}{(\alpha + \beta)^2 (\alpha + \beta + 1)} )$

---

## 6. Chi-Square Distribution

- **Description**: The distribution of the sum of squared standard normal variables. This one is ugly, and you'll be using the Chi-Square - Tables instead of this… hopefully.
- **PDF**:
  $$
  f(x) = 
  \begin{cases}
  \frac{1}{2^{k/2} \Gamma(k/2)} x^{(k/2)-1} e^{-x/2}, & x > 0 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- **Parameters**: $( k > 0 )$ (degrees of freedom)
- **Mean**: $( \mu = k )$
- **Variance**: $( \sigma^2 = 2k )$

---

## 7. Student's t-Distribution

- **Description**: Used for small sample sizes when estimating a population mean. This one is ugly, and you'll be using the T- Tables instead of this… hopefully.
- **PDF**:
  $$
  f(x) = \frac{\Gamma\left(\frac{\nu+1}{2}\right)}{\sqrt{\nu \pi} \, \Gamma\left(\frac{\nu}{2}\right)} \left(1 + \frac{x^2}{\nu}\right)^{-\frac{\nu+1}{2}}, \, x \in \mathbb{R}
  $$
- **Parameters**: $( \nu > 0 )$ (degrees of freedom)
- **Mean**: $( \mu = 0)$ (for $( \nu > 1 ))$
- **Variance**: $( \sigma^2 = \frac{\nu}{\nu-2} )$ (for $( \nu > 2 )$)

---

## 8. Log-Normal Distribution

- **Description**: Models a variable whose logarithm follows a normal distribution.
- **PDF**:
  $$
  f(x) = 
  \begin{cases}
  \frac{1}{x \sigma \sqrt{2\pi}} \exp\left(-\frac{(\ln x - \mu)^2}{2\sigma_{ln_x}}\right), & x > 0 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- **Parameters**: $( \mu \in \mathbb{R})$ (mean of log), $( \sigma > 0 )$ (standard deviation of log)
- **Mean (Expected Value)**: $( \mu_X = e^{\mu + \sigma^2 / 2} )$
- **Variance**: $( \sigma_X^2 = e^{2\mu + \sigma^2} (e^{\sigma^2} - 1) )$

---

## 9. Weibull Distribution

- **Description**: Models failure times and reliability.
- **PDF**:
  $$
  f(x) = 
  \begin{cases}
 \frac{\beta}{x})(\lambda x)^{\beta}e^{-(\lambda x)^{\beta}}, & x \geq 0 \\
  0, & \text{otherwise}
  \end{cases}
  $$
- **Parameters**:
  - $( k > 0 )$: Shape parameter
  - $( \lambda > 0)$: Scale parameter
- **Mean (Expected Value)**: $( \mu = \lambda \Gamma\left(1 + \frac{1}{k}\right) )$
- **Variance**: $( \sigma^2 = \lambda^2 \left[\Gamma\left(1 + \frac{2}{k}\right) - \left(\Gamma\left(1 + \frac{1}{k}\right)\right)^2\right] )$