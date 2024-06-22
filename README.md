
# numpy-randomPackage

![Logos](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/jupyter_python_numpy.width-808.png)


Investigating and Explanation of numpy.random package

Explain the overall purpose of the package.
Explain the use of the “Simple random data” and “Permutations” functions.
Explain the use and purpose of at least five “Distributions” functions.
Explain the use of seeds in generating pseudorandom numbers

=======
![Logos](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/jupyter_python_numpy.width-808.png)

# numpy.randomPackage
>>>>>>> 626b634f2f5d6112c711c5d7e3070a5f8e9f4d54

## Investigating and Explanation of numpy.random package

- Explain the overall purpose of the package.

- Explain the use of the “Simple random data” and “Permutations” functions.

- Explain the use and purpose of at least five “Distributions” functions.

- Explain the use of seeds in generating pseudorandom numbers

## Overview of numpy package

 I would like to give an overview background of numpy package before I dive into the explanation of purpose of numpy.random.
 
 NumPy is the fundamental package for scientific computing in Python. It is a Python library that provides a multidimensional array object, various derived objects (such as masked arrays and matrices), and an assortment of routines for fast operations on arrays, including mathematical, logical, shape manipulation, sorting, selecting, I/O, discrete Fourier transforms, basic linear algebra, basic statistical operations, random simulation and much more.Source: [numPy](https://docs.scipy.org/doc/numpy-1.15.0/user/whatisnumpy.html)
 
 Numpy is a specialisist package that is real efficient in dealing with arrays and numbers like matirx.
It is used for resizing, compressing and analysing. Anything scientifically you do on computer turns down to all of the ideas shows in matrix operations like, trying to compress image to a smaller size, compress song to a smaller size or trying to analysed data. This shows that matrix operations is the correct and quickest way to to do it. Therefore numpy is really essential because it knows how to deal with these kinds of operations very good. Source:[Lecture note Video](https://web.microsoftstream.com/video/b191f6b2-4d80-4ede-8b2b-62a945999585)

It is also a Python Package, specialized for building and manipulating large, multidimensional arrays. NumPy has built-in functions for linear alegbra and random number generation. It's an important library because a lot of the other Python packages such as SciPy, Matplotlib depend on Numpy to function (to a reasonable extent.) Source:[Github](https://github.com/simonava5/numpy.random/blob/master/numpy.random.ipynb)

Numpy.random number is a routine produce pseudo random numbers, using combinations of a BitGenerator to create sequences and a Generator to use those sequences to sample from different statistical distributions:
Numpy.randon package is use to generate simulated data.
Source: [NumPy.Random](https://numpy.org/doc/stable/reference/random/index.html#)

# Simple random data
******

## The use and purpose of the simple random data

******

We have four functions of simple random data:

- Intergars

- Random 

- Choice

- Byte

## integers 

This demonstration show what intergar function does and to discover how the function work and I will use documentation examples to discover how the function work, also to visualised it using histogram plot.

I will investigate Return random integers from low (inclusive) to high (exclusive), or if endpoint=True, low (inclusive) to high (inclusive). Replaces RandomState.randint (with endpoint=False) and RandomState.random_integers (with endpoint=True)
Return random integers from the “discrete uniform” distribution of the specified dtype. If high is None (the default), then results are from 0 to low.


- import matplotlib.pyplot as plt

- import numpy as np

- rng = np.random.default_rng()

- x = rng.integers(2, size=10)

- x

- plt.hist(x)

### Random 

****

The documentation below show what random function does and to discover how the function work, using documentation examples and visualising it with histogram plot.

I will investigate Return random floats in the half-open interval [0.0, 1.0).

Results are from the “continuous uniform” distribution over the stated interval. To sample Unif[a, b), b > a multiply the output of random by (b-a) and add a:

## Using histogram plot to visualized the function

- import numpy as np

- import matplotlib.pyplot as plt

- rng = np.random.default_rng()
- x = rng.random((10000000,))
- x

plt.hist(x)


## Choice

*****

The choice documentation show what random function does and how to discover how the function works, using documentation examples and visualising it with histogram plot.

My Investigate will be to generate a random sample from a given 1-D array

To generate a uniform random sample from np.arange(5) of size 3:

- import numpy as np

- rng = np.random.default_rng()

- rng.choice(5, 3)

This is equivalent to rng.integers(0,5,3)

## Bytes

The documentation code shows what the random function does and how to discover how the function works, using documentation example My investigation will base on return random bytes.

- np.random.default_rng().bytes(10)

 The more you press shitf + enter, the output changes
 
 ## Permutation
 
  Randomly permute  or return a permuted range. If x is a multi-dimensional array, it is only shuffle along its first index.
  
 -  rng = np.random.default_rng()

- arr = np.arange(100)

- rng.shuffle(arr)

## Gemma Distribution function

Samples are drawn from a Gamma distribution with specified parameters, shape (sometimes designated “k”) and scale (sometimes designated “theta”), where both parameters are > 0.

The Gamma distribution is often used to model the times to failure of electronic components, and arises naturally in processes for which the waiting times between Poisson distributed events are relevant.

p(x) = x^{k-1}\frac{e^{-x/\theta}}{\theta^k\Gamma(k)},

- shape, scale = 2., 2.  # mean=4, std=2*sqrt(2)
- s = np.random.default_rng().gamma(shape, scale, 1000)

## Geometric Distribution function

Draw samples from the geometric distribution.

Bernoulli trials are experiments with one of two outcomes: success or failure (an example of such an experiment is flipping a coin). The geometric distribution models the number of trials that must be run in order to achieve success. It is therefore supported on the positive integers, k = 1, 2, ....

The probability mass function of the geometric distribution is

f(k) = (1 - p)^{k - 1} p

- z = np.random.default_rng().geometric(p=0.35, size=10000)

## Logistic

Samples are drawn from a logistic distribution with specified parameters, loc (location or mean, also median), and scale (>0).

The probability density for the Logistic distribution is

P(x) = P(x) = \frac{e^{-(x-\mu)/s}}{s(1+e^{-(x-\mu)/s})^2},

where \mu = location and s = scale.

The Logistic distribution is used in Extreme Value problems where it can act as a mixture of Gumbel distributions, in Epidemiology, and by the World Chess Federation (FIDE) where it is used in the Elo ranking system, assuming the performance of each player is a logistically distributed random variable.

## Triangular Distribution function

The triangular distribution is a continuous probability distribution with lower limit left, peak at mode, and upper limit right. Unlike the other distributions, these parameters directly define the shape of the pdf.

The triangular distribution is often used in ill-defined problems where the underlying distribution is not known, but some knowledge of the limits and mode exists. Often it is used in simulations.

- import matplotlib.pyplot as plt
- h = plt.hist(np.random.default_rng().triangular(-3, 0, 8, 100000), bins=200,
             - density=True)
 
 ## Uniform Distribution function
 
Samples are uniformly distributed over the half-open interval [low, high) (includes low, but excludes high). In other words, any value within the given interval is equally likely to be drawn by uniform.

The probability density function of the uniform distribution is

p(x) = \frac{1}{b - a}

anywhere within the interval [a, b), and zero elsewhere.

When high == low, values of low will be returned. If high < low, the results are officially undefined and may eventually raise an error, i.e. do not rely on this function to behave when passed arguments satisfying that inequality condition.

## Use of Seed

# The use of seed in generating psuedorandom numbers

Generator exposes a number of methods for generating random numbers drawn from a variety of probability distributions. In addition to the distribution-specific arguments, each method takes a keyword argument size that defaults to None. If size is None, then a single value is generated and returned. If size is an integer, then a 1-D array filled with generated values is returned. If size is a tuple, then an array with that shape is filled and returned.

The Python stdlib module random contains pseudo-random number generator with a number of methods that are similar to the ones available in Generator. It uses Mersenne Twister, and this bit generator can be accessed using MT19937. Generator, besides being NumPy-aware, has the advantage that it provides a much larger number of probability distributions to choose from.

### code

- from numpy.random import Generator, PCG64
- rg = Generator(PCG64())
- rg.standard_normal()


# References:

***

(1) [Nympy](https://docs.scipy.org/doc/numpy-1.15.0/user/whatisnumpy.html)

(2) [Introduction to numpy video](https://web.microsoftstream.com/video/b191f6b2-4d80-4ede-8b2b-62a945999585)

(3) [Simple Random Data-integers function video](https://web.microsoftstream.com/video/b5c6be99-c750-4ce2-8e70-6d01f3b9dbfc)

(4) [Simple Random Data- Integers function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.integers.html#numpy.random.Generator.integers)

(5) [Simple Random Data - Random function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.random.html#numpy.random.Generator.random)

(6) [Simple Random Data - Choice function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.choice.html#numpy.random.Generator.choice)

(7) [Simple Random Data - Bytes function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.bytes.html#numpy.random.Generator.bytes)

(8) [Permutations - Shuffle function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.shuffle.html#numpy.random.Generator.shuffle)

(9) [Permutations - Permutation function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.permutation.html#numpy.random.Generator.permutation)

(10) [Distribution video](https://web.microsoftstream.com/video/e6f57177-0a17-45a5-8ca8-0e3191e887f8)

(11) [Distribution - Gamma function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.gamma.html#numpy.random.Generator.gamma)

(12) [Distribution - Geometric function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.geometric.html#numpy.random.Generator.geometric)

(13) [Distribution - Triangular function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.triangular.html#numpy.random.Generator.triangular)

(14) [Distribution Uniform function](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.uniform.html#numpy.random.Generator.uniform)

(15) [Seed video](https://web.microsoftstream.com/video/db596673-6d67-4d13-93c3-074728c693f2)

(16) [Seed in generating psuedorandom numbers](https://numpy.org/doc/stable/reference/random/index.html)

[16] [Github](https://github.com/simonava5/numpy.random/blob/master/numpy.random.ipynb)



 
