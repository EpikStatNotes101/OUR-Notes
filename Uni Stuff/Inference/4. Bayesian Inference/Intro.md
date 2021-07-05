# Intro
Bayesian Inference revolves around the idea of the Bayes' rule, which is 
$$\frac{\text{likelihood}\cdot\text{prior}}{\text{denominator}}=\text{posterior}$$
Which in term of probability distributions is
$$\frac{p(X|\theta)\cdot p(\theta)}{p(X)}=p(\theta|X)$$
While classical or frequentist Inference is just concerned with the $\text{likelihood}$

### Equivalence Principle 
The probability of data conditioned on a parameter value equals the likelihood of the parameter value given the same data

$$P(X|\theta)=L(\theta|X)$$

For $P(X|\theta)$ we vary $X$ while holding $\theta$ constant
For $L(\theta|X)$ we vary $\theta$ while holding $X$ constant