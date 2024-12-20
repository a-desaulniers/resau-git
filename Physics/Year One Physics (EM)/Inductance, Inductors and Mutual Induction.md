---
title: Inductance, Inductors and Mutual Induction
draft: false
tags:
  - Physics💡
aliases:
  - Alexandre DesAulniers
---

### Mutual Induction

Variant of Faraday's Law

$$
\epsilon_2 = -M \frac{dI_1}{dt}
$$

**ϵ** = EMF (V)
M = Mutual Inductance (H, Henrys)
I = Current (A)

- This is how wireless charging works! The magnetic field can transfer power! 
- Two coils interacting with each other

---
$$
\frac{\epsilon_2}{\epsilon_1} = \frac{N_2}{N_1}
$$
**ϵ** = EMF (V)
N = Number of Turns

- The ratio in between the two EMF's is the same as the ratio in between the amount of turns of looped wire!
- These are how **transformers work**. You can step higher voltage down to lower voltage. Power brick transformers step 120V down to 12V for our devices!
- Going from low voltage to high voltage works this way, (12V-120V), but there will always be a trade off.  
- (eg, more loops equals more resistance, (V=IR), so your voltage may be higher, but the current will drop)

##### Transformers!

---
### Self Inductance

$$
\epsilon = -L\frac{dI}{dt}
$$
**ϵ** = EMF (V)
L= Self Inductance (H, Henrys)
I = Current (A)

![[Pasted image 20240408090111.png|550]]

- L, the curly thing in the circuit, is an **INDUCTOR**

Current change over time due to this EMF

---
#### Closing the Switch (Current growing to max)

![[Pasted image 20240408102406.png|500]]

Current at a time:
$$
I(t) = I_{max}(1-e^{-\frac{1}{\tau}})
$$

Time Constant:
$$
\tau = \frac{L}{R}
$$
Half Time:
$$
t_{\frac{1}{2}} = 0.69\tau
$$

#### Opening the Switch (Current going from max to 0A)

![[Pasted image 20240408102430.png|500]]

Current at a time:
$$
I(t) = I_{max}e^{-\frac{1}{\tau}}
$$
Time Constant:
$$
\tau = \frac{L}{R}
$$

- This is cool, because this is how surge protectors work! 
- The exponential growth slows surging current, and a high inductance can slow surges. 
- The slope is nicer to electronics

![[Pasted image 20240408102132.png]]

---
#### Inductors can store and release energy! 

- This can be defined by the following equation 

$$
U = \frac{1}{2}LI^2
$$
U = Energy stored/released
L = Self Inductance (H, Henrys)
I = Current (A)