```
---
Name: Hanson Jiang
Topic: 19
Title: Fixed point iteration method and Newton's method
---
```
# Fixed point iteration method and Newton's method

## Table of Contents


* [History and Analysis](#History-and-Analysis)
	* [test](#test)
* [Description](#Description)
* [Reasons for failure](#Reasons-for-failure)
* [Special Case of Newton's Method](#Special-Case-of-Newtons-method)
    * [Example](#Example)
* [Pseudocode](#Pseudocode)
    * [Fixed-Point Iteration Method](#Fixed-Point-Iteration-Method)
    * [Newton's Method](#Newtons-Method)
* [References](#References)
## History and Analysis

The fixed-point iteration method is used to find solutions for f(x) = 0. By rewriting f(x) in such a way to define a function g such that x = g(x), we have "a fixed point of the function g, since x is unchanged when g is applied to it" (Heath, 2009, p.225).

### Fixed-Point Example
For some function $f(x)=x^2-3x-4$, we can rewrite this for fixed-point functions such as
$$g(x) = \frac{x^2-4}{3}$$

$$g(x) = \frac{4}{x-3}$$

where g(x) = x. The iteration scheme for fixed-point is as followed:
$$x_{k+1} = g(x_k)$$
with initial guess $x_0$.

An example workthrough of fixed-point iteration method using the functions above is as followed:
$$f(x)= x^2-3x-4$$
$$g(x)= \frac{4}{x-3}$$
$$x_0 = 2$$
Then we have that
$$x_1 = g(x_0) = \frac{4}{2-3} = -4$$
$$x_2 = g(x_1) = \frac{4}{-4-3} = -0.571$$
$$x_3 = g(x_2) = \frac{4}{-0.571-3} = -1.12$$
$$x_4 = g(x_3) = \frac{4}{-1.12-3} = -0.971$$
$$x_5 = g(x_4) = \frac{4}{-0.971-3} = -1.007$$
$$x_6 = g(x_5) = \frac{4}{-1.007-3} = -0.998$$
$$x_7 = g(x_6) = \frac{4}{-0.998-3} = -1.000$$
where we can approximate from fixed-point iteration that one of the roots to f(x) is -1.
Newton's method further elaborates on this by providing a more educated  
### test
* hey
## Description

* Description of methods used to solve the problem

## Reasons for failure
However, these algorithms and methods are not perfect and can fail any multidude of reasons.
### Fixed-Point Iteration Failures
"The behavior of fixed-point iteration schemes can vary widely, from divergence, to slow converge, to rapid convergence" (Heath, 2009, p.226). This means that depending on the g(x) function used, fixed-point iteration method may not actually converge.

![](fixedpoint.PNG)

As can be seen from the figure above (Heath, 2009, p.227), the top left function diverges, as each iteration takes it further away from the root. Whereas, for the other 3 functions, they do converge, but at varying speeds.
## Special Case of Newton's method
A special case of Newton's method to compute square roots is the Babylonian method, 
which was used as far back as the ancient Greek times. To approximate some value $\sqrt{S}$, if 
x is an overestimate, then $\frac{S}{x}$ would be an underestimate. The rationale was that the average of 
these two values, $\frac{1}{2}(x + \frac{S}{x})$, could be better for the $\sqrt{S}$ approximation (Fowler & Robson, 1998). With enough iterations, the approximation would 
converge to an accurate square root value.

This "average of the two values" can be equivalently deduced by employing Newton's method and solving for the roots of the function $f(x) = x^2 - S$. Newton's method can be viewed as a version of fixed-point iteration method $x = g(x)$ where $g(x)$ is defined as $g(x) = x - \frac{f(x)}{f'(x)}$ for approximation (Heath, 2009, p.229). Thus: 
$$g(x) = x - \frac{x^2 - S}{2x}$$
$$= \frac{2x^2}{2x} - \frac{x^2-S}{2x} $$
$$= \frac{1}{2}(\frac{x^2+S}{x})$$
$$= \frac{1}{2}(x + \frac{S}{x})$$
### Example
Compute/approximate $\sqrt{S}$ for $S=335$. Let initial guess $x_0=20$.
To perform Babylonian method we have $f(x)=x^2 - S$ and $g(x)=\frac{1}{2}(x + \frac{S}{x})$.

$$x_{k+1} = g(x_k) = \frac{1}{2}(x_k + \frac{S}{x_k})$$

$$x_1 = \frac{1}{2}(x_0 + \frac{S}{x_0}) = \frac{1}{2}(20 + \frac{335}{20}) = 18.375$$

$$x_2 = \frac{1}{2}(x_1 + \frac{S}{x_1}) = \frac{1}{2}(18.375 + \frac{335}{18.375}) = 18.303$$

$$x_3 = \frac{1}{2}(x_2 + \frac{S}{x_2}) = \frac{1}{2}(18.303 + \frac{335}{18.303}) = 18.303$$
For the sake of our example, 3 decimals of precision is enough. Thus we can approximate that $\sqrt{335} \approx 18.303$.
## Pseudocode
Below is pseudocode for the fixed-point iteration and Newton's method algorithms.
### Fixed-Point Iteration Method
```
1. Define f(x) from given function f(x) = 0
2. Define g(x) by converting f(x) into form x = g(x)
3. Define counter as count = 1
4. INPUT:
    x0 as initial guess
    max_iterations as maximum number of iterations
    tolerance as tolerance to stop iterations
5. for (k in max_iterations)
	x1 = g(x0)
	count = count + 1

	if count > max_iterations
	    print "Did not converge"
	    return None 

	if |x1 - x0| < tolerance
	    return x1

	x0 = x1

6. Print x1 for final result	
```
### Newton's Method
```
1. Define f(x) whose root we are looking for
2. Define fprime(x) as the derivative of f(x)
3. Define counter as count = 1
4. INPUT:
    x0 as initial guess
    max_iterations as maximum number of iterations
    tolerance as tolerance to stop iterations
5. for (k in max_iterations)
	y = f(x0)
	yprime = fprime(x0)
	count = count + 1

	if yprime == 0
	    print "Divide by zero error"
	    return None

	if count > max_iterations
	    print "Did not converge"
	    return None

	x1 = x0 - y/yprime

	if |x1 - x0| < tolerance
	    return x1

	x0 = x1

6. Print x1 for final result
```


## References

1. Fowler, D., & Robson, E. (1998). Square Root Approximations in Old Babylonian Mathematics: YBC 7289 in Context. https://doi.org/10.1006%2Fhmat.1998.2209
2. Heath, M. T. (2009). Scientific Computing: An Introductory Survey (pp. 100-30000). McGraw Hill. 
