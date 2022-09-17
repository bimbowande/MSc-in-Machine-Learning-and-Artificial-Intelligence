Partial Derivatives

You often need to compute the rate of change of multivariate functions f(x,y) with respect to the variables x and y. This is done using **partial derivatives** - derivatives of a function computed with respect to only one variable.

## Video

To get a basic understanding of partial derivatives, watch [this video on partial derivatives by Khan Academy](https://www.youtube.com/watch?v=AXqhWeUEtQU). We have summarised the concepts from this video in the section below.

## Example

Consider the following example: the volume V of a cone depends on the cone's height h and its radius r according to the following equation:

which represents the rate at which the cone's volume changes with its radius *while the height is kept constant*. The italicised part of the previous sentence is very important - while computing a partial derivative, all other variables of the function are kept constant. 
$$\large{V(r, h)=\dfrac{\pi\\r^2h}{3}}$$
The partial derivative of $V$ with respect to $r$ is:
$$\large{\dfrac{\delta\\V}{\delta\\r}=\dfrac{2\pi\\r^2h}{3}}$$
Similarly, the partial derivative with respect to the height $h$ equals:
$$\large{\dfrac{\delta\\V}{\delta\\h}=\dfrac{2\pi\\rh}{3}}$$
This rate represents how the volume of a cone (of a constant radius $r$) changes as you change the height.

#### Partial Differentiation

Qn: For the function $f(x, y)=sin(xy)+3xy$, find the value of $\dfrac{\delta\\f}{\delta\\x}$ and $\dfrac{\delta\\f}{\delta\\y}$ 

- $\dfrac{\delta}{\delta\\x}f(x, y)=y\cos(xy)+3y$ and $\dfrac{\delta}{\delta\\x}f(x, y)=x\cos(xy)+3x$

- $\dfrac{\delta}{\delta\\x}f(x, y)=y\cos(xy)+3$ and $\dfrac{\delta}{\delta\\x}f(x, y)=x\cos(xy)+3$

- $\dfrac{\delta}{\delta\\x}f(x, y)=y\cos(x)+3y$ and $\dfrac{\delta}{\delta\\x}f(x, y)=x\cos(y)+3x$

- $\dfrac{\delta}{\delta\\x}f(x, y)=cos(xy)+3y$ and $\dfrac{\delta}{\delta\\x}f(x, y)=cos(xy)+3x$

Ans:  A. 
$$\large{\dfrac{\delta}{\delta\\x}f(x, y)=f_y(x, y)=\dfrac{\delta}{\delta\\x}(sin(xy)+3xy)=cos(xy)\dfrac{\delta}{\delta\\x}+3y=y\cos(xy)+3y}$$
and
$$\large{\dfrac{\delta}{\delta\\x}f(x, y)=f_x(x, y)=\dfrac{\delta}{\delta\\y}(sin(xy)+3xy)=cos(xy)\dfrac{\delta}{\delta\\y}+3x=x\cos(xy)+3x}$$

Qn: For the function $f(x, y)=xy\ln(xy)$, find the value of $\dfrac{\delta\\f}{\delta\\x}$ and $\dfrac{\delta\\f}{\delta\\y}$ 

- $y\ ln(xy)+y$ and $x\ ln(xy)+x$ respectively.

- $ln(xy)+y$ and $ln(xy)+x$ respectively.

- $y\ ln(xy)$ and $x\ ln(xy)$ respectively.

- None of these

Ans: A.

Qn: $f(x, y, z)=x^2y+y^2z+x^2x$, what are $\dfrac{\delta\\f}{\delta\\x}$, $\dfrac{\delta\\f}{\delta\\y}$ and $\dfrac{\delta\\f}{\delta\\z}$ at $(1, 1, 1)$?

- $\dfrac{\delta\\f}{\delta\\x}=1$, $\dfrac{\delta\\f}{\delta\\y}=1$ and $\dfrac{\delta\\f}{\delta\\z}=1$

- $\dfrac{\delta\\f}{\delta\\x}=0$, $\dfrac{\delta\\f}{\delta\\y}=0$ and $\dfrac{\delta\\f}{\delta\\z}=0$

- $\dfrac{\delta\\f}{\delta\\x}=3$, $\dfrac{\delta\\f}{\delta\\y}=3$ and $\dfrac{\delta\\f}{\delta\\z}=3$

- $\dfrac{\delta\\f}{\delta\\x}=2$, $\dfrac{\delta\\f}{\delta\\y}=2$ and $\dfrac{\delta\\f}{\delta\\z}=2$

Ans: C. *$\dfrac{\delta\\f}{\delta\\x}=z^2+2xy$, $\dfrac{\delta\\f}{\delta\\y}=x^2+2yz$ and $\dfrac{\delta\\f}{\delta\\z}=y^2+2zx$ and substituting the values $(1, 1, 1)$ we'll get the values $(3, 3, 3)$*

## **Total Derivatives**

Suppose that f is a function of two variables x and y. Normally these variables are assumed to be independent. However, in some situations, they may be dependent on some other common variables. For example, both x and y themselves may be varying with time t, i.e. we can write them as x=x(t) and y=y(t).

In such cases, we cannot assume that x and y are independent (because they now depend on a common variable and are not independent), and thus, we cannot compute the partial derivatives assuming so. We rather use what are called **total derivatives.**

## Video

To get the basic understanding of total derivative, watch this video on [Multivariable chain rule](https://www.youtube.com/watch?v=NO3AqAaAE6o) by Khan Academy.

Thus, total derivatives are somewhat analogous to the rate of change of a function with respect to all its variables. Consider the function f(x,y,z) where x,y,z are functions of t . By using chain rule we can write the formula for the 'total derivative' as :
$$\large{\dfrac{\delta\\f}{\delta\\t}=\dfrac{\delta\\f}{\delta\\x}*\dfrac{\delta\\x}{\delta\\t}+\dfrac{\delta\\f}{\delta\\y}*\dfrac{\delta\\y}{\delta\\t}+\dfrac{\delta\\f}{\delta\\z}*\dfrac{\delta\\z}{\delta\\t}}$$

## Example

Let's take an example problem which can be easily solved using total derivatives. Suppose that the radius and height of a cone are both 2 cm at some time t. The radius is decreasing at the rate of 1 cm/s and the height is increasing at the rate of 2 cm/s. What is the change in volume with respect to time at an instant $t$?

We know that the volume of the cone is:
$$\large{V=\dfrac{1}{3}\pi\\r^2h}$$
Also, we are given that the radius is decreasing at the rate of 1 cm/s and the height is increasing at the rate of 2 cm/s. In other words, drdt=−1 cm/s and dhdt=2 cm/s respectively.

By using the total derivative formula, we can calculate the rate of change of volume with respect to time:
$$\large{\dfrac{\delta\\V}{\delta\\t}=\dfrac{\delta\\V}{\delta\\r}*\dfrac{dr}{dt}+\dfrac{\delta\\V}{\delta\\h}*\dfrac{dh}{dt}}=\dfrac{2}{3}\pi\\rh*\dfrac{dr}{dt}+\dfrac{1}{3}\pi\\r^2*\dfrac{dh}{dt}$$
$$\large{=\dfrac{2}{3}\pi(2)(2)*(-1)+\dfrac{1}{3}\pi(2)^2*(2)=-\dfrac{8}{3}\pi+\dfrac{8}{3}\pi=0}$$
Hence, we can say that the volume of the cone is not changing at this time point t.

#### Total Derivative

Qn: Recall the formula for the total derivative, that is, for $f(x, y), x=x(t)$ and $y=y(t)$:
$$\dfrac{\delta\\f}{\delta\\t}=\dfrac{\delta\\f}{\delta\\t}\dfrac{dx}{dt}+\dfrac{\delta\\f}{\delta\\t}*\dfrac{dy}{dt}$$
Given that $f(x, y)=\pi^2x^2y$, $x(t)=t^2+1$ and $y(t)=t2−1$, calculate the total derivative $\dfrac{df}{dt}$.

- $\dfrac{df}{dt}=2\pi(t^2+1)2(t^2-1)+\pi(t^2+1)2(t^2-1)$

- $\dfrac{df}{dt}=4\pi^2t(t^2+1)(t^2-1)+2\pi^2t(t^2+1)^2$

- $\dfrac{df}{dt}=8\pi^2t(t^2+1)(t^2-1)$

- $\dfrac{df}{dt}=8\pi\\t(t^2+1)2(t^2-1)+2\pi\\t(t^2+1)^2$

Ans: B. 