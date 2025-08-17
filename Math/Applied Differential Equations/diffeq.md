---
title: Applied Differential Equations
draft: false
tags:
  - Mathematics
---
Before we begin!

I would like to give a special thank you to:

- [Guy Kember](https://www.dal.ca/faculty/engineering/math-internetworking/people/people-profiles/guy-kember.html), Professor of Engineering Mathematics at Dalhousie University

- [Patrick Reynolds](https://www.unb.ca/faculty-staff/directory/science-fr-math/reynolds-patrick.html), Professor of Mathematics and Statistics at the University of New Brunswick

-  [Karsten Economou](https://orcid.org/0000-0002-4367-2582), Graduate Researcher at the Department of Engineering Mathematics & Internetworking at Dalhousie University
  
- [Hossein Mostafavi Sani](https://scholar.google.com/citations?user=uigiSG8AAAAJ&hl=en), Graduate Mechanical Engineering at Dalhousie University 

- [Paul Dawkins](https://tutorial.math.lamar.edu/classes/de/de.aspx), Professor of Mathematics and Statistics at Lamar University | Maintainer of Paul's Online Notes

For their contributions in Mathematical education, and provision of knowledge for this wiki tree. The following notes are my second year class notes for Applied Differential Equations, and I hope you may find them helpful!

These notes will be updated periodically, and put in order of what I believe to be most helpful. 


![[A-simple-differential-equation-representing-a-theory-driven-model.png]]

---

#### First Order Systems

- [[1.1 Basic Theory.pdf|Basic Theory]]
- [[Lecture 4, Models.pdf|First Order LTI Models]]
- [[Lecture 2 (Karsten).pdf|First Order LTI Models, solved using Method of Undetermined Coefficients]]
- [[1.2 Non-Homogeneous DE's with Constant Coefficients.pdf|First Order MUC Contd. & Variation of Parameters]]
- [[Lecture 5 (Karsten).pdf|First Order LTI Models, MUC Method cont. Multiple Yp's]]


---
#### Second Order Systems

- [[Yh Walkthrough.pdf|Explanation of Yh in Second Order Systems]]
- [[Yp Walkthrough.pdf|Explanation of Yp (Oscillator Guesses) in Second Order Systems, Using the Auxiliary method]]
	- *(if you do not have oscillators, you can just make a regular Yp guess, as was done with first order LTI*
- [[1.3 Applications.pdf|Practical Applications of Systems]]
- [[Full Worked Out Examples.pdf |Worked Out Yp & Yh Examples]]
- [[Second Order Example, Two Yp's.pdf|Worked Out Harder Multi-Yp Oscillator Problem]]
- [[Sketching Second Order DE's + Oscillio.pdf|Sketching Second Order DE's and Oscilliators]]
- [[Transfer Function.pdf|Transfer Function Example Problem]]
---
#### Systems of Differential Equations

- [[2.1 Systems of DE's.pdf|Systems of Differential Equations, & Practical Solutions]]
- [[2.2 Solving With Eigen.pdf|Solving Systems of DE's using Eigen's]]
- [[2.3 Vector Fields.pdf|Systems of DE's, relating to Vector Fields]]

- [[3.1 Second Order Systems of DE's.pdf|Second Order Systems of Differential Equations]]
- [[3.2 Repeated Eigenvalues.pdf|Repeated Eigen's, & Higher Multiplicities]]
- [[3.3 Matrix Exponentials.pdf|Matrix Exponentials]]
- [[3.4 Non Homogenous Systems.pdf|Non-Homogenous Systems]]

---
#### LaPlace Transformations 

>[!example] LaPlace Transform Table:
>
> |$T$|$S$ |
> |---------|---------|
> | $1$  | $\frac{1}{s}$|
> | $t$  | $\frac{1}{s^2}$  |
> | $t^n$  | $\frac{n!}{s^{n+1}}$   |
> | $\sin(kt)$  | $\frac{k}{k^2 + s^2}$  |
> |  $\cos(kt)$   | $\frac{s}{k^2 + s^2}$  |
> | $e^{at}$   | $\frac{1}{s - a}$  |
> | $\delta(t)$ | $1$ |
> | $\delta(t - a)$  | $e^{-as}$  |
> | $U(t - a)$  | $\frac{e^{-as}}{s}$  |
> | $e^{at} f(t)$ | $F(s - a)$ $\text{   FIRST SHIFT THEOREM}$  |
> | $( f(t - a)U(t - a)$  | $e^{-as}F(s). \text{  SECOND SHIFT THEOREM. USE ONLY FOR LAPLACE INVERSION}$  |
> | $( g(t)U(t - a)$  | $e^{-as}L[g(t + a)]. ) \text{  SECOND SHIFT THEOREM. USE ONLY FOR LAPLACE TRANSFORMING}$  |
> | $( f^{(n)}(t)$  | $s^n F(s) - s^{n-1} f(0) - s^{n-2} f^{(1)}(0) - \dots - f^{(n-1)}(0) )$ |
> | $( t^n f(t)$  | $(-1)^n F^{(n)}(s) )$  |
> | $( (f * g)(t)$  | $\int_0^t f(u)g(t - u)du = \int_0^t f(t - u)g(u)du, F(s)G(s) )$  |

- [[laplace_intro.pdf|Intro to LaPlace Transforms]]
- [[Switches & Step Functions.pdf|Switches & Step Functions]]
	- [[Switches.pdf|Switches contd.]]

- [[Delta Functions.pdf|Delta Functions]]
---
#### Fourier Series & Boundary Value Problems

- [[4.1 Boundary Value Problems & Trigonometric Series.pdf|Boundary Value Problems & Trigonometric Series]]
- [[4.2 General Fourier.pdf|General Fourier Construction]]
- [[Fourier Series.pdf|Advanced Uses - Fourier Series]]

---
#### Additional Items of Note

[[Completing the Square.pdf|Completion of the Square]]