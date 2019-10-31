
# Mathematical Notation

## Introduction

In this lesson, we'll learn how to read some of the more common mathematical notation that you'll see when reading equations pertaining to Data Science.

## Objectives

You will be able to:

* Read and understand basic mathematical notation


## Understanding Mathematical Notation

When learning Data Science, running into dense, arcane-looking mathematical equations is an inevitability. For instance, here's an equation for a machine learning algorithm called a _Support Vector Machine_ that you'll touch upon later in the course


$ \large \text{minimize:} $

$$ \large W(\alpha) = - \sum_{i=1}^{\ell}\alpha_i + \frac{1}{2}\sum_{i=1}^{\ell}\sum_{j=1}^{\ell}y_iy_j\alpha_i\alpha_j\textbf{x}_i\textbf{x}_j$$


$ \large \text{subject to:} $ $$ \large \sum_{\substack{i=1 \\ 0\leq\alpha_i\leq C}}^{\ell}y_i \alpha_i = 0 $$


<strong><em>Don't stare at this too long, or else you'll get a nosebleed...</em></strong></center>

At first glance, equations like this often seem impenetrable and impossible to understand. If seeing math like this makes you nervous, don't worry -you're not alone! 

This is a particularly dense example of mathematical notation, but at the end of the day, it's just a recipe for an algorithm. Whereas we are used to expressing our algorithms in code, mathematicians prefer to use **_Mathematical Notation_**, to express big ideas in small, dense packages full of Greek letters, subscripts, and superscripts. Although these look intimidating in the beginning, they'll seem a lot more manageable once we've learned some basic mathematical notation. 

There are many, many mathematical symbols. We'll touch on the two very important ones here: the **_Summation_** symbol and the **_Product_** symbol. You'll use some of these in what's coming next, looking more in-depth at summary metrics such as the mean (you actually created a function for this in the previous lab!) and the variance.

## Sigma Notation (Summations)

In the equation above, you'll notice the following symbol appears:

$$\large \sum $$

This is called **_Sigma Notation_**, and is a way of notating **_Summation_**. 

Consider the following code:

```python
sum_total = 0
n = 5
for i in range(1, n+1):
    sum_total += i
```

This is pretty simple code - just a for-loop that calculates the sum total of every number between 1 and 5, inclusive (meaning it stops after including 5 in the total, not before, which is why we put `n+1` in the range instead of just `n`).

A mathematician would express the same algorithm using the following **_Sigma Notation_**:

$$\large \sum_{n=1}^{5} x $$

Pretty nifty, huh? The equation above says that we should start counting at 1, because we see `n=1` under the summation. We should stop once we've hit 5 (inclusive). Our sum totals the sum of each value of X for each step between `n=1` and up to (and including) `n=5`. 

If we were to write it out explicitly, it would look like:

$$\large \sum_{n=1}^{5} x = 1 + 2 + 3 + 4 + 5 $$

This was the most simple example of summation since we were just adding in the individual value at each step in the example above. However, we can put anything we want to the right of the Sigma symbol, and this will be what happens at each step. For example, let's consider the following code:

```python
def f(x):
    return x**2 - 2

sum_total = 0
n = 5
for i in range(1, n+1):
    sum_total += f(i)
```

In the code above, we have a simple function that returns the square of a number, minus 2. This time, the for loop calculates the sum of that function called on every number between 1 and 5, inclusive.  We can write the exact same thing in Sigma Notation as follows:

$$\large \sum_{n=1}^{5}x^2-2$$

Which, if "unrolled" to show each step, would look like: 

$$\large \sum_{n=1}^{5}x^2-2 = (1^2 - 2) + (2^2 - 2) + (3^2 - 2) + (4^2 - 2) + (5^2 - 2) $$

Finally, let's consider what this looks like when working with arrays. 

Consider the following code:

```python
w = [2.2, 3, -2, 4]
x = [0.25, 0, 1, -2]

sum_total = 0

for i in range(len(w)):
    sum_total += w[i] * x[i]
```

In the above example, we use the counter in our for loop as the index to get each subsequent element out of `w` and `x` and multiply them together. We can denote the same thing with Sigma Notation as follows:

$$\large \sum_{i=1}^{w} w_i x_i $$

**_NOTE:_** Can you spot the difference? In our for loop, our index starts at 0, while in our Sigma Notation, our index starts at 1. In practice, they still mean the same thing--start at the first element in each list, multiply them, and add them to the sum, and then continue until we've done that for every item in the list `w`. The Sigma Notation starts at 1 because mathematicians start counting at 1, whereas programmers start counting at 0. **_Remember this--it'll save you from buggy code later on!_** 

## Pi Notation (Products)

Another common type of notation is **_Pi Notation_**, which works similarly to Sigma Notation. The only real difference here is that Pi Notation multiplies each step, rather than adds them to a total. With our understanding of Sigma Notation, it isn't that hard to figure out an example of Pi Notation. 

```python
total = 1
n = 5

for i in range(1, n+1):
    total *= i + 2
```

In Pi Notation, this would translate to:

$$ \large \prod_{i=1}^{5} i + 2$$

Which, when written out completely, would be:

$$ \large \prod_{i=1}^{5} i + 2 = (1 + 2) * (2 + 2) * (3 + 2) * ( 4 + 2) * ( 5 + 2)$$

As you can see from the example above, there isn't too much of a difference between sigma and pi notation. The only difference is that with Sigma, you add the results of each step, whereas with Pi, you multiply them!


## Summary

In this lesson, we learned about how to read basic Sigma and Pi Notation.
