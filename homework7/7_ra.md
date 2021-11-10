**Made by Nicolò Baroncini (1834907)**

## Research about application(7_RA)
### Do a research about the random walk process and its properties.
In mathematics, a random walk is a mathematical object, known as a stochastic or random process, that describes a path that consists of a succession of random steps on some mathematical space such as the integers.

An elementary example of a random walk is the random walk on the integer number line which starts at 0 and at each step moves +1 or −1 with equal probability.\
In the simplest context the walk is in discrete time, that is a sequence of random variables (Xₜ) = (X₁, X₂, ...) indexed by the natural numbers. However, it is also possible to define random walks which take their steps at random times, and in that case, the position X
t has to be defined for all times t ∈ [0,+∞).

Various types of random walks are of interest, which can differ in several ways. The term itself most often refers to a special category of Markov chains but many time-dependent processes are referred to as random walks, with a modifier indicating their specific properties. \
A Markov chain or Markov process is a stochastic model describing a sequence of possible events in which the probability of each event depends only on the state attained in the previous event.

There are numerous properties of random walks that we may be interested in. They are listed and defined below.

**Stationary distribution** \
A stationary distribution of a Markov chain is a probability distribution that remains unchanged in the Markov chain as time progresses. Typically, it is represented as a row vector π whose entries are probabilities summing to 1, and given transition matrix P, it satisfies

![image](https://user-images.githubusercontent.com/78324346/141069829-3ad727e6-30f5-4ae6-ab3f-572b50eeeca2.png)

Below follows an exampleof stationary distribution:

A sports broadcaster wishes to predict how many Michigan residents prefer University of Michigan teams (known more succinctly as "Michigan") and how many prefer Michigan State teams. She noticed that, year after year, most people stick with their preferred team; however, about 3% of Michigan fans switch to Michigan State, and about 5% of Michigan State fans switch to Michigan. However, there is no noticeable difference in the state's population of 10 million's preference at large; in other words, it seems Michigan sports fans have reached a stationary distribution. What might that be?

A reasonable way to approach this problem is to suppose there are x million Michigan fans and y million Michigan State fans. The state's population is 10 million, so x + y = 10. These numbers do not change each year. It follows that

![image](https://user-images.githubusercontent.com/78324346/141070356-bb9260b0-56ae-42d2-8d40-4756a4b0d0d6.png)

Rearranging either equation, x = (5/3)y. Since x+y=10, y = (3/8)10 = 3.75 and x = 6.25. So there are 6.25 million Michigan fans and 3.75 million Michigan state fans. In other words, the stationary distribution is (0.625, 0.375).


**Hitting time** \
**Commute time** \
**Cover time**


### Compare your finding with your applications drawing your personal conclusions.

### Explain based on your exercise the beaviour of the distribution of the stochastic process (check out "Donsker's invariance principle"). What are, in particular, its mean and variance at time n ?

[1][https://en.wikipedia.org/wiki/Random_walk](https://en.wikipedia.org/wiki/Random_walk) \
[2][http://pages.cs.wisc.edu/~shuchi/courses/787-F07/scribe-notes/lecture27.pdf](http://pages.cs.wisc.edu/~shuchi/courses/787-F07/scribe-notes/lecture27.pdf) \
[3][https://en.wikipedia.org/wiki/Markov_chain](https://en.wikipedia.org/wiki/Markov_chain) \
[4][https://brilliant.org/wiki/stationary-distributions/](https://brilliant.org/wiki/stationary-distributions/)
