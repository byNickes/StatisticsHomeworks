**Made by Nicolò Baroncini (1834907)**

## Research about application(7_RA)
### Do a research about the random walk process and its properties.
In mathematics, a random walk is a mathematical object, known as a stochastic or random process, that describes a path that consists of a succession of random steps on some mathematical space such as the integers.

In the simplest context the walk is in discrete time, that is a sequence of random variables (Xₜ) = (X₁, X₂, ...) indexed by the natural numbers. However, it is also possible to define random walks which take their steps at random times, and in that case, the position X
t has to be defined for all times t ∈ [0,+∞).

A natural way to think about the random walk is in term of paths. The outcome path s =
(s1, s2, . . .) can be identified with the sequence (t, st), t = 0, 1, . . . of ordered pairs, or better yet with the graph of the piecewise linear function that connects the points (t, st) as shown in the next figure.

![image](https://user-images.githubusercontent.com/78324346/141074983-cfe6a37d-eedf-44bd-ba99-d4ae0ea75fb9.png)

Of those paths there are infinite.

Various types of random walks are of interest, which can differ in several ways. Let's see two of them.

##### Simple random walk
Let X₁,..., Xₜ,... be a sequence of independent Rademacher random variables

![image](https://user-images.githubusercontent.com/78324346/141072631-9d05e4fa-cafc-45a4-b1fb-f61699b3163e.png)

so E Xₜ = 0 and Var Xₜ = 1 (t = 1,2,...)

The index t indicates a point in time. Feller uses the term epoch to denote a particular
moment t, and reserves the use of the word “time” to refer to a duration or interval of time,
rather than a point in time. The set of epochs is the set {0,1,2,...} of non negative integers.\

For each t, is defined the running sum as Sₜ = X₁ + · · · + Xₜ and S0 = 0.\
It follows that for each Sₜ:

E Sₜ = 0 and Var Sₜ = t.

The sequence of random variables S₀, . . . , Sₜ, . . .  where t ∈ {0,1,2,...} is a discrete-time stochastic process known as the simple random walk on the integers.

Talking about the asymptotics of this random walk we have that:

**1-** The Strong Law of Large Numbers tells us that

![image](https://user-images.githubusercontent.com/78324346/141073950-9125a13b-4010-42d5-8ed2-03e13e6dde5c.png)

**2-** The Central Limit Theorem tells us that

![image](https://user-images.githubusercontent.com/78324346/141074012-72e0db2f-674f-467c-ab06-a2b6d79d2a01.png)

#### Random walk from Normal Distribution
This is a random walk where the random values are drawn from a normal probability distribution with mean μ = 0 and unit standard deviation σ = 1. \
So let's consider the following random walk

![image](https://user-images.githubusercontent.com/78324346/141076647-57b55e9d-61dc-4152-a724-47b05b12d284.png)

in which each dₜ is a IID Normal random variable with mean 0 and variance 1. We know that each xₙ is Normal with mean 0 and variance σ² = n.\
As a function of n, the probability densities boraden as n increases without changing their shape.

Sinche σ = √n is a measure of the deviation of x from its mean 0, then the size of xₙ is O(√n). So we have added together n terms, each of which is O(1), but the result is not of size O(n) but rather O(√n). This is due to cancelations of the di since they come with both positive and negative values. This cancelation is the hearth of the Central Limit Theorem.



### Compare your finding with your applications drawing your personal conclusions.


### Explain based on your exercise the beaviour of the distribution of the stochastic process (check out "Donsker's invariance principle"). What are, in particular, its mean and variance at time n ?

[1][https://en.wikipedia.org/wiki/Random_walk](https://en.wikipedia.org/wiki/Random_walk) \
[2][http://pages.cs.wisc.edu/~shuchi/courses/787-F07/scribe-notes/lecture27.pdf](http://pages.cs.wisc.edu/~shuchi/courses/787-F07/scribe-notes/lecture27.pdf) \
[3][https://en.wikipedia.org/wiki/Markov_chain](https://en.wikipedia.org/wiki/Markov_chain) \
[4][https://brilliant.org/wiki/stationary-distributions/](https://brilliant.org/wiki/stationary-distributions/)\
[5][http://www.math.caltech.edu/~2016-17/2term/ma003/Notes/Lecture16.pdf](http://www.math.caltech.edu/~2016-17/2term/ma003/Notes/Lecture16.pdf) \
[6][https://people.revoledu.com/kardi/tutorial/StochasticProcess/RandomWalk/Normally-Distributed-Random-Walk.html](https://people.revoledu.com/kardi/tutorial/StochasticProcess/RandomWalk/Normally-Distributed-Random-Walk.html) \
[7][https://www.math.ucla.edu/~caflisch/181.1.03f/Lect4-5.pdf](https://www.math.ucla.edu/~caflisch/181.1.03f/Lect4-5.pdf)
