**Made by Nicolò Baroncini (1834907)**

## Research about application(9_RA)
### Try to find on the web what are the names of the random variables that you just simulated in the applications, and see if the means and variances that you obtain in the simulation are compatible with the "theory". If not fix the possible bugs.
Below are listed the names and characteristics of the variables we have computed in the 13_A application.\
Since in the application mentioned above are already plotted the theoretical mean and variance of each distribution, it's possible to see that the empirical variances and means obtained are all around the theoretical value. So, it's not wrong to say that the computation of the distributions has not errors.

**Log-normal distribution**\
A log-normal distribution is a continuous probability distribution of a random variable whose logarithm is normally distributed.\
Thus, if the random variable X is log-normally distributed, then Y = ln(X) has a normal distribution. Equivalently, if Y has a normal distribution, then the exponential function of Y, X = exp(Y), has a log-normal distribution.\
A random variable which is log-normally distributed takes only positive real values.

*Generation and parameters*\
Let Z be a standard normal variable, and let μ and σ>0 be two real numbers. Then, the distribution of the random variable

![image](https://user-images.githubusercontent.com/78324346/143195092-e3d62763-e87f-446d-9032-631dc5f5b83e.png)

is called the log-normal distribution with parameters μ and σ.

The mean of this distribution is

![image](https://user-images.githubusercontent.com/78324346/143195266-cf9c16b8-70fb-4c96-bb2c-231154d9f4c3.png)

The variance is

![image](https://user-images.githubusercontent.com/78324346/143195314-ad26a208-78f7-4ae9-81eb-0b4f67f37ae4.png)

**Chi-squared distribution**\
The chi-squared distribution with k degrees of freedom is the distribution of a sum of the squares of k independent standard normal random variables.

*Generation and parameters*\
If Z1, ..., Zk are independent, standard normal random variables, then the sum of their squares,

![image](https://user-images.githubusercontent.com/78324346/143196151-98525390-1da3-496d-91dc-e52768dfd8e4.png)

is distributed according to the chi-squared distribution with k degrees of freedom.

The chi-squared distribution has one parameter: a positive integer k that specifies the number of degrees of freedom (the number of random variables being summed).

The mean of the distribution is k.

The variance of the distribution is 2k.

[1][https://en.wikipedia.org/wiki/Log-normal_distribution](https://en.wikipedia.org/wiki/Log-normal_distribution)\
[2][https://en.wikipedia.org/wiki/Chi-squared_distribution](https://en.wikipedia.org/wiki/Chi-squared_distribution)
