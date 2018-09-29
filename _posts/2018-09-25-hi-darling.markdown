---
layout: post
title:  "Hi Darling!"
date:   2018-09-25 22:55:46 +0100
categories: jekyll update
math: true
---

$$\require{cancel}$$

A friend recently shared a funny joke on Facebook and challenged me to solve it. Here it is:

![My helpful screenshot](/assets/images/integral_pin.png)

A caring person leaves her debit card to her partner and invites him to use it how he wishes. Only condtion, to find the PIN code he must solve a difficult integral. Can we help him to find the solution?

First, let's factorise the numerator. I will start by dividing by $$x-1$$:


$$
	\begin{array}{rrrr|rrr}
	3x^3 & -x^2 & +2x & -4 & x & -1 & \\
	\hline
	-3x^3 & +3x^2 & & & 3x^2 & & \\
	& 2x^2 & +2x & -4 &  & & \\
	& -2x^2 & +2x & & & +2x & \\
	& & 4x & -4 & & & \\
	& & -4x & +4 & & & +4 \\
	& & & 0 & & & 
	\end{array}
$$ 

so that 

$$3x^3-x^2+2x-4=(x-1)(3x^2+2x+4)$$

This is as far as we can go since the quadratic term does not have real roots. We can also factorise the polynomial under square root at the denominator:

$$x^2-3x+2=(x-1)(x-2)$$

Given the form of the integrand we can use [Euler substitution](https://en.wikipedia.org/wiki/Euler_substitution):

$$\sqrt{x^2-3x+2}=x+t$$

So that squaring both sides and simplifying:

$$\cancel{x^2}-3x+2=(x+t)^2=\cancel{x^2}+2xt+t^2$$

$$2-t^2=2xt+3x=x(2t+3)$$

$$x=\frac{2-t^2}{2t+3}$$

The differential also transforms accordingly:

$$
	\begin{array}{rl}
	dx&=-\dfrac{2t(2t+3)+2(2-t^2)}{(2t+3)^2}dt \\
	&=-2\dfrac{t^2+3t+2}{(2t+3)^2}dt \\
	&=-2\dfrac{(t+1)(t+2)}{(2t+3)^2}dt 
	\end{array}
$$

Let's see how the factors involved in the integral transform:

$$
	\begin{array}{rl}
	x-1 & \rightarrow\dfrac{2-t^2-2t-3}{2t+3}=-\dfrac{(t+1)^2}{2t+3} \\
	x-2 & \rightarrow\dfrac{2-t^2-4t-6}{2t+3}=-\dfrac{(t+2)^2}{2t+3} \\
	3x^2+2x+4 & \rightarrow 3\dfrac{(2-t^2)^2}{(2t+3)^2}+2\dfrac{2-t^2}{2t+3}+4 \\
	& = \dfrac{3t^4-4t^3-2t^2+56t+60}{(2t+3)^2} 
	\end{array}
$$

The interval of integration also transforms:

$$
	\begin{array}{rl}
	0 & \rightarrow t=\sqrt{2} \\
	1 & \rightarrow 2-t^2=2t+3 \rightarrow t^2+2t+1 = 0 \rightarrow t=-1
	\end{array}
$$

The initial integral becomes:

$$
\begin{array}{rl}
& \displaystyle\int_{\sqrt{2}}^{-1}2\dfrac{(t+1)^2}{\cancel{2t+3}}\dfrac{3t^4-4t^3-2t^2+56t+60}{(2t+3)^2}\dfrac{\cancel{2t+3}}{\cancel{(t+1)(t+2)}}\dfrac{\cancel{(t+1)(t+2)}}{(2t+3)^2}dt \\
& =\displaystyle\int_{\sqrt{2}}^{-1}2\dfrac{(t+1)^2(3t^4-4t^3-2t^2+56t+60)}{(2t+3)^4}dt
\end{array}
$$