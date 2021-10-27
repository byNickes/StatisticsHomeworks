**Made by Nicolò Baroncini (1834907)**

## Research about application(5_RA)
### Do a web research about the various methods to generate, from a Uniform([0,1)), all the most important random variables (discrete and continuous). Collect all source code you think might be useful code of such algorithms (keep credits and attributions wherever applicable), as they will be useful for our next simulations.

#### Discrete distributions

• ***Bernoulli distribution*** \
The  Bernoulli distribution is the discrete probability distribution of a random variable which takes the value 1 with probability p and the value 0 with probability q = 1-p.
The parameters of this distribution are:

Ω = {0,1}, x ∈ Ω
p = Probability of x=1 (0 ≤ p ≤ 1)

To generate this distribution can be used the inverse trasformation generating u = U(0,1) and if u ≤ p then return 0, otherwise return 1.
A possible code to generate a random value from the Bernoulli distribution could be the one below.
```C#
double p = 0.4;
Random r = new Random()
double u = r.NextDouble();
if(u <= p) return 0;
else return 1;
```
• ***Binomial distribution*** \
The Binomial distribution, with parameters n and p, is the discrete probability distribution of the number of successes in a sequence of n independent experiments, each asking a yes–no question, and each with its own Boolean-valued outcome: success (with probability p) or failure (with probability q = 1 − p). A single success/failure experiment is also called a Bernoulli trial or Bernoulli experiment.

The parameters of this distributions are:

Ω = {0,1, ...., n}, x ∈ Ω
p = Probability of success in a trial, 0 < p < 1.
n = Number of trials, n must be a positive integer.

[1][https://www.cse.wustl.edu/~jain/books/ftp/ch5f_slides.pdf](https://www.cse.wustl.edu/~jain/books/ftp/ch5f_slides.pdf) \
[2][https://en.wikipedia.org/wiki/Bernoulli_distribution](https://en.wikipedia.org/wiki/Bernoulli_distribution) \
[3][https://en.wikipedia.org/wiki/Binomial_distribution](https://en.wikipedia.org/wiki/Binomial_distribution)
