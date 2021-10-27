**Made by Nicolò Baroncini (1834907)**

## Research about application(5_RA)
### Do a web research about the various methods to generate, from a Uniform([0,1)), all the most important random variables (discrete and continuous). Collect all source code you think might be useful code of such algorithms (keep credits and attributions wherever applicable), as they will be useful for our next simulations.

#### Discrete distributions

• ***Discrete uniform distribution***
The discrete uniform distribution is a symmetric probability distribution wherein a finite number of values are equally likely to be observed. Every one of n values has equal probability 1/n. \
The PDF of this distribution is the following: \
![image](https://user-images.githubusercontent.com/78324346/139026894-e3bddbfa-6f64-443f-b093-523109deb838.png)
The parameters of this distribution are:
a,b integers with b ≥ a, n = b-a+1 \
The formula of the PDF is 

![image](https://user-images.githubusercontent.com/78324346/139027185-a4780ebe-7c1c-4b79-a5e8-cd260aaf0084.png)

To generate a random number from the discrete uniform distribution, one can draw a random number R from the U(0, 1) distribution, calculate S = (n + 1)R, and take the integer part of S as the draw from the discrete uniform distribution. 

• ***Bernoulli distribution*** \
The  Bernoulli distribution is the discrete probability distribution of a random variable which takes the value 1 with probability p and the value 0 with probability q = 1-p.
The PDF of this distribution is the following:\
![image](https://user-images.githubusercontent.com/78324346/139028179-69e1f5c2-ca26-47ee-9997-c558b4d7097b.png)
The formula of the PDF is
The parameters of this distribution are:
Ω = {0,1}, k ∈ Ω
p = Probability of k=1 (0 ≤ p ≤ 1)

![image](https://user-images.githubusercontent.com/78324346/139028670-0b747696-9adf-4814-ba2a-270ebe6ce7b4.png)

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

To generate this distribution can be used the inverse transformation method. \
Compute the CDF F(x) for x = 0, 1, 2, . . ., n and store in an array. For each binomial variate, generate a U(0,1) variate u and search the array to find x so that F(x) ≤ u < F(x + 1) and finally return x.

• ***Poisson binomial distribution***
The Poisson binomial distribution is the discrete probability distribution of a sum of independent Bernoulli trials that are not necessarily identically distributed.

The parameter of this distribution are:
 Ω = {0, 1, 2, . . . , ∞}, x ∈ Ω, λ = Mean (λ > 0)

The formula of the PDF is:

 ![image](https://user-images.githubusercontent.com/78324346/139025878-f632f54a-20e2-4176-a68a-8c9a676557af.png)

To generate this distribution can be used the inverse transformation method. \
Compute the CDF F(x) for x = 0, 1, 2, . . . up to a suitable cutoff and store in an array. For each Poisson random variable, generate a u = U(0,1), and search the array to find x such that F(x) ≤ u < F(x + 1), then return x.

[1][https://www.cse.wustl.edu/~jain/books/ftp/ch5f_slides.pdf](https://www.cse.wustl.edu/~jain/books/ftp/ch5f_slides.pdf) \
[2][https://en.wikipedia.org/wiki/Bernoulli_distribution](https://en.wikipedia.org/wiki/Bernoulli_distribution) \
[3][https://en.wikipedia.org/wiki/Binomial_distribution](https://en.wikipedia.org/wiki/Binomial_distribution)\
[4][https://en.wikipedia.org/wiki/Poisson_binomial_distribution](https://en.wikipedia.org/wiki/Poisson_binomial_distribution) \
[5][https://en.wikipedia.org/wiki/Discrete_uniform_distribution](https://en.wikipedia.org/wiki/Discrete_uniform_distribution) \
[6][https://www.sciencedirect.com/topics/mathematics/discrete-uniform-distribution](https://www.sciencedirect.com/topics/mathematics/discrete-uniform-distribution)
