---
title:  "Recurrence Relations and Exponential Functions"
date: "2015-12-13"
slug: "recurrence-relations-and-exponential-functions"
---
In my Higher Maths class we have just finished the recurrence relations topic and as part of that we investigated the limit of recurrence relations.  We also plotted some example as \\(n \rightarrow \infty\\) so we could see the behaviour of \\(u_n\\). I actually wrote a Shiny [app][Shinyapp] to show the behaviour. The graphs led to a question about the relationship between \\(u_n\\) as \\(n\\) increases and exponential functions. 


If we start we a recurrence relation of the form 

$$u_{n+1} = au_n + b$$

with some value of \\(u_0\\) then we can very quickly find out what \\(u_1\\), \\(u_2\\) etc. are. If we look at the first few terms we get

$$\begin{align}
u_1 &= au_0 + b \\
u_2 &= au_1 + b = a(au_0 + b) + b = a^2u_0 + ab + b \\
u_3 &= au_2 + b = a(a^2u_0 + ab + b) + b = a^3u_0 + a^2b + ab + b \\
u_4 &= au_3 + b = a(a^3u_0 + a^2b + ab + b) \\
&= a^4u_0 + a^3b + a^2b + ab + b.
\end{align}$$

This pattern continues so we end up with 

$$u_n = a^nu_0 + a^{n-1}b + a^{n-2}b + \ldots + a^2b + ab + b$$

or rather 

$$u_n = a^nu_0 + b\left(\sum_{k = 0}^{n-1}a^k\right)$$

where \\(\sum\\) means sum all the terms so

$$\sum_{k = 0}^{n-1}a^k = a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1.$$

It can be shown (and I've included a quick proof at the bottom of this post) that

$$\sum_{k = 0}^{n-1}a^k = \frac{a^n - 1}{a - 1}$$

and so putting all of this together gives

$$u_n = a^nu_0 + b\left(\sum_{k = 0}^{n-1}a^k\right) = a^nu_0 + \frac{b\left(a^n - 1\right)}{a - 1}.$$

We can choose \\(u_0 = 0\\) just to make this look easier in this case and we end up with

$$u_n = \frac{b\left(a^n - 1\right)}{a - 1}.$$



So we now have an expression for \\(u_n\\) that involves the exponential \\(a^n\\) we were expecting. Remember that \\(a\\) and \\(b\\) are just numbers. If we take an example recurrence relation 

$$u_{n+1} = 4u_n + 6$$

then we will have 

$$u_n = \frac{b\left(a^n - 1\right)}{a - 1} = \frac{6\left(4^n - 1\right)}{4 - 1} = 2\left(4^n - 1\right).$$



This expression we now have for \\(u_n\\) also lets us prove the limit for a recurrence relation. If \\(-1 < a < 1\\) then \\(a^n\\) will get very small as \\(n\\) gets very big. After a certain point \\(n\\) will be so big that \\(a^n\\) might as well be zero. We can prove this formally but I'm not going to do it here. If we take \\(a^n\\) to be zero then we get

$$u_n = \frac{b\left(a^n - 1\right)}{a - 1} = \frac{b\left(0 - 1\right)}{a - 1} = \frac{-b}{a - 1}$$

and if we multiply top and bottom by \\(-1\\) we end up with

$$u_n = \frac{b}{1 - a}.$$

### Footnote: Proof of summation
To find the sum of \\(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\\) is surprisingly straight forward. We start by multiplying the whole thing by \\(a - 1\\).

$$\left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right)\left(a - 1\right) = a\left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right) - \left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right)$$

Multiply out gives us

$$\left(a^{n} + a^{n-1} + a^{n-2} + \ldots + a^2 + a\right) - \left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right)$$

and you'll see that almost everything cancels except the very first and very last terms.

$$\begin{align}
& \left(a^{n} + a^{n-1} + a^{n-2} + \ldots + a^2 + a\right) - \left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right) \\
&= a^{n} + a^{n-1} - a^{n-1} + a^{n-2} - a^{n-2} + \ldots + a^2 - a^2 + a - a + 1 \\
&= a^n - 1
\end{align}$$

So we can write 

$$\left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right)\left(a - 1\right) = a^n - 1.$$

Remembering our summation notation above

$$\left(a^{n-1} + a^{n-2} + \ldots + a^2 + a + 1\right)\left(a - 1\right) = \left(\sum_{k = 0}^{n-1}a^k\right)\left(a - 1\right) = a^n - 1$$

so if we divide both sides by \\(a - 1\\) we get

$$\begin{align}
\frac{\left(\sum_{k = 0}^{n-1}a^k\right)\left(a - 1\right)}{a - 1} &= \frac{a^n - 1}{a - 1} \\
\sum_{k = 0}^{n-1}a^k &= \frac{a^n - 1}{a - 1}
\end{align}$$

finishing our proof.



[Shinyapp]:		https://shiny.aj2duncan.com/higher/rec_rel/
