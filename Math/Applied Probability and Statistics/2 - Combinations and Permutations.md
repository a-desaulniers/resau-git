---
title: Combinations and Permutations
draft: false
tags:
  - Mathematics
---
**Counting Principles:**

- Often outcomes are equilikely, but there are numerous possibles. How can we figure out the number of possible outcomes?
	- Can use a tree diagram, but usually takes FOREVER, especially with a large initial set
	- ![[PXL_20240910_114139446.jpg]]

- We can use what's called the **Multiplication rule** to speed things up.

##### Multiplication Rule

If an experiment has <font color="#c0504d">k</font> stages, and 
1) Stage 1 has <font color="#c0504d">m<sub>1</sub> </font> possible outcomes,
2) Stage 1 has <font color="#c0504d">m<sub>2</sub> </font> possible outcomes,
3) ...
4) Stage K has <font color="#c0504d">m<sub>k</sub> </font> possible outcomes,

then the total number of possible outcomes is

n = <font color="#c0504d">m<sub>1</sub> </font>* <font color="#c0504d">m<sub>2</sub> </font> * ...  *<font color="#c0504d">m<sub>k</sub> </font>

Usually, one sets it up like this using dashes

$$
\underline{2} \space\space\space \underline{2} \space\space\space \underline{2} \rightarrow 8
$$

---

#### Example 1


![[PXL_20240910_115132948.jpg]]

Total outcomes are n = <font color="#c0504d">m<sub>k</sub></font>, The second half is an aside. 

It turns out, the probability of each outcome occurring is 

$$
\frac{1}{m^k}
$$

Pretty low right?

---
#### Example 2

##### a) How many ways can 6 unique people line up?

$$
\underline{6} \space\space\space \underline{5} \space\space\space \underline{4} \space\space\space \underline{3} \space\space\space \underline{2} \space\space\space \underline{1}   \rightarrow n =6(5)(4)(3)(2)(1) = 6!
$$

6!, or about **720** unique ways. 


##### <u>b)</u> Two people are friends, and want to stand to stand together in the line up

$$
(\underline{5} \space\space\space \underline{4} \space\space\space \underline{3} \space\space\space \underline{2} \space\space\space \underline{1}) \times 2   \rightarrow 240
$$

##### <u>c)</u> Two people have a fight and now refuse to stand next to each other in the line up.

720 is the total number of ways that these two can be together, and not together. Here, we already know the total amount of ways that they are together, that being 240.

so...

$$
n = 720 -240 =480
$$

So the answer is 480 distinct ways. 

---
#### <u>Special Cases</u>

- **Permutations**:
	-  An arrangement of distinct objects, *where order matters* (*ex, "ab" versus "ba"*)
	- If *r* objects are selected from *m* objects, then the number of *permutations* is

$$
n = \frac{m!}{(m-r)!} = P_r^m
$$

In the case of our six person line up from earlier, the order mattered. (*ie, who wants to be in line first, etc*) 
In that case, 

m = 6
r =6


$$
n = \frac{6!}{(6-6)!} =\frac{6!}{0!} = \frac{6!}{1} =6! =\underline{720}
$$


---
#### Example 3

Consider the four letters a,b,c and d. 

a) <u>What are all the permutations of these letters taken at a time?</u>

m = 4
r = 1 

$$
n = \frac{4!}{(4-1)!} = \frac{4!}{3!} = \underline{4}
$$

b) <u>What are all the permutations of these letters taken two at a time?</u>


m = 4
r = 2

$$
n = \frac{4!}{(4-2)!} = \frac{4!}{2!} = \frac{4\times3\times2\times1}{2\times1} = 4\times 3 = \underline{12}
$$


What are they?

			ab ba
			ac ca
			ad da
			bc cb 
			bd db 
			ad cd


n = 12.

---

- **Combinations**: ^8b383e
	- An arrangement of distinct objects where order does not matter.

$$
n = \frac{m!}{(m-r)!r!} = \text{m}\space \underline{choose} \space\text{r}
$$
---
#### Example 4

How many combinations can we have choosing two letters from a,b,c and d?

m =4 
r=2

$$ 
n = \frac{4!}{(4-2)!2!} = \frac{4\times3\times2\times1}{(2\times1)(2\times1)} =\frac{4 \times 3}{2\times1} =\underline6
$$
---

#### Example 5 

A company keeps a list of eight software suppliers. Not all suppliers are asked to provide a quote on a given request. Determine the number of ways 3 suppliers can be chosen from the list.

m = 8 
r =3

We have determined here that order does not matter. It doesn't matter in which order we choose the suppliers. **We can use a combination here**

$$
n = \frac{8!}{(5!)3!}
$$

Incomplete! He has it in his notes, I could not finish it. 

---


#### Example 7

Suppose you have been dealt (randomly) 13 cards from a bridge deck. What is the probability that they are all spades? What interpretation did you use to access this probability?

Now,

m = 52
r = 13 

Does order matter in this case? **No.**

$$
n = \frac{52!}{(52-13)!12!} = \frac{52!}{39!13!} = {52\times51... \times41!\times40}{13\times12\times...\times2\times1} = \underline{635,013,559,598} \approx \underline{6.4\times10^{11}}
$$

So the probability of you getting 13 spades in a row is

$$
\frac{1}{6.4\times10^{11}}
$$

That's a pretty low chance!!


> [!note] 
> *The total possible sets of 13 cards randomly is 635,013,559,598, or 6.4x10<sup>11</sup>*

---

#### <u>Mathematics of Probability</u>

How do we compute the probability of an event?, *P{events}*

**We start with 3 fundamental assumptions that have been studied in Statistics for centuries.**

1) P{A}  ≥  0

2) The certain event, P{s}  = 1  
		 Probability is a number between 0 and 1 that says how likely something is to occur: **0 means it's impossible.** **1 means it's certain.**

3) For any sequence of <font color="#c0504d">disjoint</font> events, the probability of their unions, is just the sum of their probabilities. 
*or*
$$
P(A_1 \cup A_2 \space \cup... \cup \space A_n) = P(A_1) + P(A_2)... P(A_n)
$$

![[PXL_20240910_124019106.jpg|600]]

#### <u>Here are some important results...</u>

![[PXL_20240910_124513615.jpg]]

e) **for any two events**

$$ 
P(A\cup B) = P(A) +P(B) - P(A\cap B)
$$

![[PXL_20240910_124837876.jpg]]

**If we have three, or more events,** 

You'll want to add all the probabilities of each, and subtract the intersections 

![[PXL_20240910_125053955.jpg]]

**This is the general case**

---

However, if they are disjoint!! (*I,e not overlapping on the Venn diagram* ) It makes life a whole lot easier. ^5cd4bb

$$
\text{If disjoint}, P(A\cup\space B \cup\space C \cup\space D) = P(A) + P(B) + P(C) + P(D)
$$

This will save you a **lot of time**.

---

In the thick of it, you will probably want to refer to probability using the number over 100 (*i,e 0.82, or 0.54*) instead of percentages (*i,e 82% or 54%*), like you'd usually hear when discussing probability.

It makes things much easier to add, and multiply. 