---
title: "Completing the square"
date: "2013-11-06"
---
<p>I was covering "completing the square" in class today and one of the examples caused a little difficulty. I thought I would use it as a chance to test a new plug-in for this site.</p>
<p>The question involved was: Use completing the square to solve \( 2x^2 = 3x+6 \).</p>
<p>We begin by rearranging and setting equal to zero</p>
<p>$$ 2x^2-3x-6=0 $$</p>
<p>and then remove the common factor of 2. I tend to remove it just from the first 2 terms to avoid fractions in the third term - this doesn't actually matter in this case but I will continue with the method I used in class</p>
<p>$$2x^2-3x-6 = 2\left(x^2-\frac{3}{2} \right) - 6. $$</p>
<p>Now we can completing the square:</p>
<p>$$2\left(x^2-\frac{3}{2} \right) - 6 = 2\left[\left(x-\frac{3}{4}\right)^2-\frac{9}{16}\right]-6.$$</p>
<p>In this step we, halved the \(\frac{3}{2}\) to get the \(\frac{3}{4}\) and the \(-\frac{9}{16}\) comes from need to cancel the extra \(\frac{9}{16}\) that is created from multiplying out</p>
<p>$$\left(x-\frac{3}{4}\right)^2 = \left(x-\frac{3}{4}\right)\left(x-\frac{3}{4}\right) = x^2-\frac{3}{4}x + \frac{9}{16}.$$ Finally we simplify to get $$2\left[\left(x-\frac{3}{4}\right)^2-\frac{9}{16}\right]-6 =  2\left(x-\frac{3}{4}\right)^2-\frac{18}{16}-6 = 2\left(x-\frac{3}{4}\right)^2-\frac{57}{8}.$$</p>
<p>We have now finished completing the square and know that</p>
<p>$$ 2x^2-3x-6= 2\left(x-\frac{3}{4}\right)^2-\frac{57}{8}.$$</p>
<p>Onto actually solving \( 2x^2-3x-6=0\). We use our work from above because it doesn't factorise neatly so</p>
<p>$$\begin{align} 2x^2-3x-6 & = 0 \\ 2\left(x-\frac{3}{4}\right)^2-\frac{57}{8} &= 0 \\ 2\left(x-\frac{3}{4}\right)^2 & = \frac{57}{8} \\ \left(x-\frac{3}{4}\right)^2  &= \frac{57}{16}<br />
\end{align}$$</p>
<p>Now we need to get rid of the \(^2\) by taking the square root, remembering that we're now expecting to use both the postive and negative roots.</p>
<p>$$\begin{align} \left(x-\frac{3}{4}\right)^2  &= \frac{57}{16} \\  x-\frac{3}{4}  &= \pm \sqrt{\frac{57}{16}} \\ x &= \pm\sqrt{\frac{57}{16}} + \frac{3}{4}<br />
\end{align}$$</p>
<p>Which gives the correct answer but we could simplify things - first notice that we can take the square root of 16 on the denominator and then we can make things look a little nicer.</p>
<p>$$ x = \pm\sqrt{\frac{57}{16}} + \frac{3}{4} = \pm\frac{\sqrt{57}}{4}+\frac{3}{4} = \frac{\pm\sqrt{57}+3}{4} $$</p>
<p>So our final answers are</p>
<p>$$ x=\frac{\sqrt{57}+3}{4} \quad \text{or} \quad x=\frac{-\sqrt{57}+3}{4}$$</p>
