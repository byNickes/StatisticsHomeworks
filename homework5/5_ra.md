**Made by Nicolò Baroncini (1834907)**

## Research about application(5_RA)
### Do a web research about the various methods to generate, from a Uniform([0,1)), all the most important random variables (discrete and continuous). Collect all source code you think might be useful code of such algorithms (keep credits and attributions wherever applicable), as they will be useful for our next simulations.

#### Discrete distributions

• ***Discrete uniform distribution***\
The discrete uniform distribution is a symmetric probability distribution wherein a finite number of values are equally likely to be observed. Every one of n values has equal probability 1/n. \
The PDF of this distribution is the following: 

![image](https://user-images.githubusercontent.com/78324346/139026894-e3bddbfa-6f64-443f-b093-523109deb838.png?s=5)

The parameters of this distribution are:\
a,b integers with b ≥ a, n = b-a+1

The formula of the PDF is the following

![image](https://user-images.githubusercontent.com/78324346/139200645-c0be2742-2383-4b64-8608-db64abae777b.png)

To generate a random number from the discrete uniform distribution, one can draw a random number R from the U(0, 1) distribution, calculate S = (n + 1)R, and take the integer part of S as the draw from the discrete uniform distribution. 

• ***Bernoulli distribution*** \
The  Bernoulli distribution is the discrete probability distribution of a random variable which takes the value 1 with probability p and the value 0 with probability q = 1-p. \
The PDF of this distribution is the following:

![image](https://user-images.githubusercontent.com/78324346/139028179-69e1f5c2-ca26-47ee-9997-c558b4d7097b.png)

The parameters of this distribution are: \
Ω = {0,1}, k ∈ Ω \
p = Probability of k=1 (0 ≤ p ≤ 1)

The formula of the PDF is the following

![image](https://user-images.githubusercontent.com/78324346/139200755-266a1134-9e92-4c1d-87c2-77003ae4ab77.png)

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
The Binomial distribution, with parameters n and p, is the discrete probability distribution of the number of successes in a sequence of n independent experiments, each asking a yes–no question, and each with its own Boolean-valued outcome: success (with probability p) or failure (with probability q = 1 − p). A single success/failure experiment is also called a Bernoulli trial or Bernoulli experiment.\
The PDF of this distribution is the following:

![image](https://user-images.githubusercontent.com/78324346/139126221-22b8c52c-f30b-48af-9572-75127caf49dc.png)

The formula of the PDF is the followingù

![image](https://user-images.githubusercontent.com/78324346/139200850-83bcf06d-464d-4888-a79d-f5781cf61cf6.png)

The parameters of this distributions are:\
Ω = {0,1, ...., n}, x ∈ Ω \
p = Probability of success in a trial, 0 < p < 1\
n = Number of trials, n must be a positive integer\

To generate this distribution can be used the inverse transformation method. \
Compute the CDF F(x) for x = 0, 1, 2, . . ., n and store in an array. For each binomial variate, generate a U(0,1) variate u and search the array to find x so that F(x) ≤ u < F(x + 1) and finally return x. \
The formula of the CDF needed for this algorithm is \
![image](https://user-images.githubusercontent.com/78324346/139125527-69d13ac5-a890-40ab-a354-6bf086d6e104.png)

• ***Poisson distribution***\
The Poisson binomial distribution is the discrete probability distribution of a sum of independent Bernoulli trials that are not necessarily identically distributed.

The parameters of this distribution are: \
 Ω = {0, 1, 2, . . . , ∞}, x ∈ Ω, λ = Mean (λ > 0) \
The PDF of this distribution is the following:

![image](https://user-images.githubusercontent.com/78324346/139126314-e5475652-2781-4bc4-8752-e4ddf763888f.png)

The formula of the PDF is:

![image](https://user-images.githubusercontent.com/78324346/139200955-2c61bf0c-9705-440d-b33c-38f706a48d92.png)

To generate this distribution can be used the inverse transformation method. \
Compute the CDF F(x) for x = 0, 1, 2, . . . up to a suitable cutoff and store in an array. For each Poisson random variable, generate a u = U(0,1), and search the array to find x such that F(x) ≤ u < F(x + 1), then return x. \
The formula of the CDF needed for this algorithm is\
![image](https://user-images.githubusercontent.com/78324346/139201018-b8133a52-042e-42e7-98e5-5ee9d8520232.png)

#### Continuous distributions

• ***Uniform distribution*** \
The continuous uniform distribution is a family of symmetric probability distributions. The distribution describes an experiment where there is an arbitrary outcome that lies between certain bounds. The bounds are defined by the parameters, a and b, which are the minimum and maximum values. The interval can either be closed or open. Therefore, the distribution is often abbreviated U (a, b), where U stands for uniform distribution.

The parameters of this distribution are: \
a = Lower limit \
b = Upper limit, b > a \
The PDF of this distribution is the following: 

![image](https://user-images.githubusercontent.com/78324346/139201535-7dcd869e-c81f-424a-a189-12285d267628.png)

The formula of the PDF is:

![image](https://user-images.githubusercontent.com/78324346/139202084-ffeaea51-4017-445c-ab4a-3d2c3508effe.png)

To generate U(a, b), generate u = U(0, 1) and return a + (b − a)*u.

• ***Exponential distribution*** \
The exponential distribution is the probability distribution of the time between events in a Poisson point process, i.e., a process in which events occur continuously and independently at a constant average rate.

The parameters of this distribution are: \
a = Scale parameter = Mean, a > 0 \
The PDF of this distribution is the following:

![image](https://user-images.githubusercontent.com/78324346/139202660-26fe3b72-2518-4561-a2c9-f82773f7d1f8.png)

The formula of the PDF is:

![image](https://user-images.githubusercontent.com/78324346/139202974-50f2fef5-00d0-417b-b488-6c471f5a0008.png)

To generate this distribution can be used the inverse transformation method. \
Generate a u = U(0,1) and return −a*ln(u) as Exp(a).

• ***Normal distribution*** \
In probability theory, a normal distribution is a type of continuous probability distribution for a real-valued random variable. Normal distributions are important in statistics and are often used in the natural and social sciences to represent real-valued random variables whose distributions are not known.

The parameters of this distribution are: \
µ = Mean\
σ = Standard deviation, σ > 0\
The PDF of this distribution is the following:

![image](https://user-images.githubusercontent.com/78324346/139203695-ff545bb3-f629-45bf-a421-d7797c630d51.png)

The formula of the PDF is:

![image](https://user-images.githubusercontent.com/78324346/139204024-90912729-a8f7-4383-874a-235aecf800e3.png)

This distribution can be generated using the sum of a large number of uniform uᵢ = U(0, 1):

![image](https://user-images.githubusercontent.com/78324346/139204444-3e50b991-1f9a-4983-af89-4793b1374db3.png)

Generally, n = 12 is used.


[1][https://www.cse.wustl.edu/~jain/books/ftp/ch5f_slides.pdf](https://www.cse.wustl.edu/~jain/books/ftp/ch5f_slides.pdf) \
[2][https://en.wikipedia.org/wiki/Bernoulli_distribution](https://en.wikipedia.org/wiki/Bernoulli_distribution) \
[3][https://en.wikipedia.org/wiki/Binomial_distribution](https://en.wikipedia.org/wiki/Binomial_distribution)\
[4][https://en.wikipedia.org/wiki/Poisson_binomial_distribution](https://en.wikipedia.org/wiki/Poisson_binomial_distribution) \
[5][https://en.wikipedia.org/wiki/Discrete_uniform_distribution](https://en.wikipedia.org/wiki/Discrete_uniform_distribution) \
[6][https://www.sciencedirect.com/topics/mathematics/discrete-uniform-distribution](https://www.sciencedirect.com/topics/mathematics/discrete-uniform-distribution) \
[7][https://en.wikipedia.org/wiki/Continuous_uniform_distribution](https://en.wikipedia.org/wiki/Continuous_uniform_distribution) \
[8][https://en.wikipedia.org/wiki/Exponential_distribution](https://en.wikipedia.org/wiki/Exponential_distribution) \
[9][https://en.wikipedia.org/wiki/Normal_distribution](https://en.wikipedia.org/wiki/Normal_distribution)
