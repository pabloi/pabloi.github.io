---
layout: post
title:  "Weber's law and the coding of stimuli in the brain"
date:   2019-08-30 20:02:12 -0300
categories: proofs science perception
---


After reading the article 'The mechanistic foundation of Weber's law' ([Pardo-Vazquez et al., Nature, 2019][pv]), I decided to derive the implications of Weber's law in the coding of stimuli assuming a drift-difussion model. 
Specifically, I'll show that under a simple drift-difussion model of decision-making, Weber's law implies that stimulus coding has to follow a power-law.

## Two-alternative choice perceptual tasks
Two-alternative perceptual tasks are tasks in which a subject is asked some question about some stimuli, and can only answer one of two alternatives.
For example, this can be a yes/no or a left/right task. 
A specific type of two-alternative tasks is one where two stimuli are presented and subjects are asked to order them according to some property (e.g. which is the louder sound, or the fastest moving image, etc.).
Here I will refer to this type of task, although the derivation can hold more generally for any symmetric-choice task.

## The drift-difussion model for perceptual decision making
The main assumption is that perceptual decision making is done through a drift-diffusion process, which is a random process where evidence is accumulated until a decision barrier or threshold is reached. 
More specifically, the process is characterized as a Wiener process with drift:
$$ dx = adt + bdw $$
Where $$dw$$ is a zero-mean gaussian process differential, and $$dt$$ is the time differential, and thus $$a$$ is the drift rate (that is, the expected rate of evidence accumulation), and $$b$$ is the difussion rate (that is, the standard deviation of the accumulation of evidence) of the process.
Notably, both $$a$$ and $$b$$ can be functions of the presented stimuli. In a two-alternative task, we may define the stimuli as $$s_1$$ and $$s_2$$, so $$a=a(s_1,s_2)$$ and $$b=b(s_1,s_2)$$.
Suppose that the two alternatives are symmetric, such that we can assume the process starts at $$x=0$$, and a decision is made when x reaches 1 or -1, representing the two possible choices respectively.
If we define $$ \lambda(s_1,s_2) = \frac{a}{b^2} $$, then the probability that subjects will choose the first alternative is:

$$
p(\text{choice}=1) = \frac{1}{1+e^{-\lambda}} 
$$

See [Wagenmakers et al. 2007][wag] for more information on this model, including the distribution of reaction times on the task.

## Weber's law
Weber's law states that the probability of correctly ordering two stimuli (i.e. answering correctly the question 'which is the larger stimulus?') depends only on the ratio of stimuli intensity. That is: 

$$
p(\text{correct}) = f(s_1/s_2) 
$$

If we notice that being correct means selecting the specific stimulus (1 or 2) that was the larger one, we can equate the previous two equations. 
This implies that $$\lambda $$ as defined above can only be a function of the ratio $$s_1/s_2$$.
However, we do not expect either $$a$$ or $$b$$ to be solely a function of this ratio.
In principle, both may show a more complicated dependence on the stimuli presented.
If we adopt the alternative representation (without loss of generality) $$a(s_1,s_2)=\bar{a}(s_1 s_2, s_1/s_2) $$ and $$b(s_1,s_2)=\bar{b}(s_1 s_2, s_1/s_2) $$, which is merely expressing the functional dependence of $$a$$ and $$b^2$$ in terms of a scale factor ($$\bar{s} = s_1 s_2$$) and a contrast factor ($$\delta = s_1/s_2$$).
The fact that $$\frac{a}{b^2}$$ simplifies to $$g(s_1/s_2)$$ implies that the following factorization is possible:

$$
\bar{a} = h(\bar{s}) g_a(\delta) 
$$

$$
\bar{b}^2 = h(\bar{s}) g_b(\delta)
$$

Note that the dependence on the scale factor is the same for both, so they cancel out when taking the ratio.

## Coding of stimuli in the brain
How are different stimulus magnitudes represented in the brain?
Here we will further assume that the evidence accumulation process results from the the comparsion of two independent neural representations, one for each stimuli. 
Further, we will assume that both representations are equivalent, that is, that there are no preferred stimuli (although this is not necessary for the main result below).
We will use $$r(s)$$ to represent the mean (i.e. expected) neural activity for each stimulus, and $$q^2(s)$$ to represent its variance.
Under the independence assumption, we have:

$$
a(s_1,s_2) = r(s_1) - r(s_2)
$$

$$
b^2(s_1,s_2) = q^2(s_1) + q^2(s_2)
$$

This is equivalent to stating that each stimulus is coded in neural activity such that the activity has an expected value of $$r(s)$$ and a variance $$q(s)$$.
In order to find the implications of Weber's law on the coding of stimuli in the brain we will equate the two alternative expressions for the drift rate that we have so far:

$$
a(s_1,s_2) = r(s_1) - r(s_2) = h(s_1 s_2) g_a(s_1/s_2) = \bar{a} (\bar{s},\delta) 
$$

Now, we take the cross partial derivative $$\frac{\partial^2 a}{\partial s_1 \partial s_2}$$:

$$
0 = \frac{\partial^2 a}{\partial s_1 \partial s_2} = \frac{\partial^2 \bar{a}}{\partial s_1 \partial s_2} = g_a \left( f' + \bar{s} f'' \right) - \frac{f}{s_2^2} \left( g_a'' \delta +g_a' \right)
$$

Where the cross derivative of the first expression resolves to 0 because of the independence in stimulus coding.
We can then rearrange terms and substitute the expression $$s_2^2 = \bar{s} \delta^{-1}$$ to obtain:

$$
\bar{s}\frac{f' + \bar{s} f''}{f} = \delta \frac{g_a'' \delta + g_a'}{g_a}
$$

Where the left-side expression is a function only of $$\bar{s}$$ and the right-side only of $$\delta$$.
Consequently, the two sides need to resolve to a constant value for the equality to hold for any value of the stimuli.
This results in the following differential equation:

$$
 \bar{s}^2 f'' + \bar{s}f' = \gamma^2 f
$$

Where $$\gamma^2$$ is the aforementioned constant value. The function $$g_a$$ satisfies the same differential equation on the variable $$\delta$$.
For $$\gamma \neq 0$$ the solutions to this equation take the power-law form:

$$
f= A\bar{s}^\gamma + B\bar{s}^{-\gamma}
$$

With arbitrary $$A$$ and $$B$$. The same expression results for $$g_a$$. Further, for $$g_a$$ the equivalence of stimuli ($$a(s_1,s_2)=-a(s_2,s_1)$$) implies $$A=-B$$.
This results in:

$$
r(s) = A s^{\gamma} - B s^{-\gamma}
$$

 Which is the linear combination of two inverse power-laws. Thus, **Weber's law implies power-law coding of stimuli in the nervous system under a simple decision-making model**. 
Notably, this proposed coding of stimuli is physiologically implausible outside a limited range when the term associated with the positive exponent is non-zero: it implies rapidly growing levels of neural activity with stimulus size.

Going through the same derivation for $$b^2$$, we can verify that Weber's law is satisfied with the following specific form:

$$
\lambda = C \text{tanh}(\gamma \text{log}(\delta))
$$

Note that for the special case $$\gamma=0$$ solutions are of the form $$f=A \text{log}(\bar{s}) + B$$, which results in $$r(s)= A\text{log}^2(s) + B \text{log}(s)$$, and $$\lambda = C \text{log} \delta$$ after imposing equivalence of stimuli.
These appear to be physiologically plausible, so they need to be considered an alternative to the power-laws above.
Further, if $$ \gamma < 0 $$ the results above hold but the exponents are complex, so we obtain trigonometric functions instead of power-laws.
Those solutions appear less physiologically plausible.

## Comparison to Pardo-Vazquez et al. 2019
The article by [Pardo-Vazquez et al.][pv] derives a similar result in the context of a principle they call TIED, which generalizes Weber's law and states that the effect of scale on decision making is equivalent to a time rescaling.
Their result is stronger than the one shown here because it starts from a simpler assumption (just that the decision-making process can be modeled as a Continuous Markov Process, CMP) and derive the drift-difusion process with fixed barriers as described above as a consequence of TIED (strictly speaking, the fixed barriers drift-diffusion process is just one of two possible solutions they find). 
On the flip side,  their derivation requires more work to achieve a result that contains the one I am showing here.

Notably, the derivation in the article adds some further assumptions (on top of TIED and CMPs) to constrain the family of solutions found.
One of those assumptions is that the two stimuli presented in a two-alternative task are coded by independent neural populations (as is assumed here).
Thus, the proof presented clarifies that this independence assumption along with Weber's law is sufficient to reproduce some of their results, independently of TIED.
Relatedly, the article does not find the solutions presented here corresponding to the cases of $$\gamma=0$$ and $$\gamma <0$$.
As best as I can tell, this is because the TIED requirement imposes a stronger constraint than Weber's law on the solutions. 
Specifically, TIED requires the exact same temporal rescaling for any given change in scale (e.g. if stimuli magnitude is increased tenfold, then decision time is halved regardless of what the original stimuli were), whereas Weber's law along with fixed-barriers drift-diffusion models only imply that there must exist a temporal rescaling, but that rescaling need not be simply a function of the change in magnitudes (e.g. if stimuli are increased tenfold from a magnitude of 1 to 10 then decision time is halved, but a tenfold increase from 10 to 100 may result in only a 10% reduction of decision time). 
Whatever the case, I believe the derivation presented here has value because both drift-difussion models and Weber's law are well-accepted in the perceptual decision-making literature, and thus the coding result is implied under those two assumptions independently of TIED.  

## Final comments
Here I've shown that **Weber's law implies power-law coding of stimuli in the nervous system under a simple decision-making model** (or at least that power-laws are part of a small subset of possible solutions).
But does this type of coding actually happen in the brain? 

That is what [Pardo-Vazquez et al.][pv] convincingly suggest through their experimental results on mice and men (actually, rats and both men and women). 
However, my own research seems to contradict this result: I could not fit both accuracy of responses and reaction times in a two-alternative leg-speed discrimination task (in preparation!) under a power-law coding assumption. 
Specifically, I was unable to fit the empirical accuracy vs. reaction time curve using this model.
In short, it seems that the relative scaling of the drift and noise terms needed to fit this curve is different from the ones that can be obtained under the power-law assumption.  
Because Weber's law has not been tested in the specific perceptual task I am using, it is possible that the whole framework simply does not apply. 
Testing the validity of Weber's law and TIED in leg-speed discrimination tasks is on our lab's to-do list.


[pv]: https://www.nature.com/articles/s41593-019-0439-7
[wag]: https://link.springer.com/article/10.3758/BF03194023
