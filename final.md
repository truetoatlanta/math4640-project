```
---
Name: Hanson Jiang
Topic: 19
Title: Fixed point iteration method and Newton's method
---
```
# Fixed point iteration method and Newton's method

## Table of Contents


* [Section 1](#Section-1)
	* [test](#test)
* [Section 2](#Section-2)
* [Section 3](#Section-3)
* [Pseudocode](#Pseudocode)
	* [Fixed-Point Iteration](#Fixed-Point-Iteration)
	* [Newton's Method](#Newtons-Method)
* [References](#References)
## Section 1

* An appropriate explanation of the key points of the topic
### test
* hey
## Section 2

* Description of methods used to solve the problem

## Section 3

* Here talk about the special case of Newton's method
* Is Newton's method technically a special case of fixed point?

## Pseudocode
### Fixed-Point Iteration
```
f(x): given function where f(x) = 0
g(x): convert f(x) into form x = g(x)
x0: initial guess
<pre>
<b>for</b> k=0,1,2,...
	x1 = g(x0)
<b>end</b></pre>
End iterations if maximum iterations or error tolerance reached.	
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
	y0 = f(x0)
	yprime = fprime(x0)
	count = count + 1

	if yprime == 0
	    print "Divide by zero error"
	    return None

	if count > max_iterations
	    print "Did not converge"
	    return None

	x1 = x0 - y0/yprime

	if |x1 - x0| < tolerance
	    return x1

	x0 = x1

6. Print x1 for final result
```


## References

1. References
2. Can
3. Go
4. Here
5. Like
6. This
7. Bryngelson, S. H., & Freund, J. B. (2018). Global stability of flowing red blood cell trains. Physical Review Fluids, 3(7). https://doi.org/10.1103/physrevfluids.3.073101 

## ANYTHING BELOW THIS IS NOT IN THE PAPER DRAFT
## ---------------------
## Formatting 

Use "Github" flavored markdown, which is a slightly more powerful version of usual markdown. The file extension is usually `.md`.
You can include equations in usual LaTeX-like way, $Ax=b$, or like this
$$Ax=b.$$

![](images.png)

You can also include images like this (notice that the image file is in the repository)! 

![](example_gif.gif)

You can also include `.gif`s!

Pseudocode is included via triple backticks, like this
```
Pseudocode
Can
Go 
Here
```
and inline code can `go like this`.

Here are some links for Github-flavored markdown syntax that could be helpful:
* https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
* https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

## Length

The length of your article is flexible. 
However, I understand it is useful to put some bounds on things.

Here are some example articles that are too short
* http://www.scholarpedia.org/article/Fixed_point
* http://www.scholarpedia.org/article/Normal_forms
* https://en.wikipedia.org/wiki/Numerical_method

Here is one that [is probably too long](https://en.wikipedia.org/wiki/Floating-point_arithmetic) for this project, though I will certainly not mark you down if you write something this comprehensive!

## Audience

Write your article such that it could be understood by a student who is about to take this course, but hasn't started yet (you just a few months ago!).
For example, [here is one](http://www.scholarpedia.org/article/WENO_methods) that is presented in a way that is too complex for your mock audience. 

## How you will be graded

From the `topics.md` document: 
> Some of these topics may be easier or harder to write about depending on at what length they were discussed in class. This will be taken into account while grading, with somewhat fewer details and less depth expected for more complex or well-discussed topics.

### Rubric

* 60% __Technical correctness and completeness.__ Get full points here by
	* Not saying things that are technically incorrect. 
	* Completeness is a bit nebulus here. You do not need to include _everything_ you could possibly discuss about your topic (that could be an entire textbook in some cases!). 
	Instead, include a combination of breadth and depth that is in line with some of the Wikipedia/Scholarpedia examples provided. 
	* In many cases you should include some equations and pseudocode to explain your topic, though there are a few exceptions to this.
	* Not mentioning a method that is critical to your topic could result in deducted points, especially if that topic was discussed at length in class.

* 20% __Clarity.__ Get full points here by
	* Not including topics that are irrelevant to yours (at least not without explanation of why they are there!). 
	* Do include reference to topics, via links and proper references, that are relevant to yours. 
	* Use hyperlinks to navigate around your document (for example, [like this](https://stackoverflow.com/questions/2822089/how-to-link-to-part-of-the-same-document-in-markdown)). 
	* Make your document intellectually accesssible to your mock audience (discussed above). 
	* No non sequiturs.
	* Use proper English grammar. 
	* No spelling mistakes.

* 10% __Presentation.__ Get full points here by
	* Using high quality graphics (if you use graphics). 
	* Consistent style.
	* Proper use of tables, figures, lists (bulleted and numerated), etc.
	* _Make it something you would be proud to show to your colleagues!_

* 10% __Organization.__ Get full points here by 
	* Separate and organize sections and subsections appropriately. 
	* Include a table of contents
	* References and URL refs. in an appropriate location.

