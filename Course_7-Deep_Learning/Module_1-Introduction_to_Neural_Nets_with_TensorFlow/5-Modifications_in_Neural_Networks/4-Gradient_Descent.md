# Gradient Descent

In this segment, you shall start with the basics of the gradient descent algorithm and the different problems faced in it and then move on to the different optimization techniques that are used in most of the industry level problems in the segments that follow.

You have already been introduced to the gradient descent algorithm in the previous sessions. Let us reiterate it before moving ahead.

The **gradient descent** is an optimisation algorithm used to find the minimum value of a function. The basic idea is to use the gradient of the function to find the direction of the steepest descent, i.e., the direction in which the value of the function decreases most rapidly, and move towards the minima iteratively according to the following rule:
$$\large{w_{new}=w_{old}−\alpha.\dfrac{\delta\\L}{\delta\\w}}$$
$$\large{b_{new}=b_{old}−\alpha.\dfrac{\delta\\L}{\delta\\b}}$$

Where $\alpha$ is the learning rate which determines how quickly or slowly the model learns and attains the minimum value.

So far you have been dealing with minima of the given curve but there are various different points on a curve that you might encounter on your search for the minima. Let us learn about them in the upcoming video:

**VIDEO**

In the above video, you learnt about **critical points** which can be points of minima and maxima or **saddle points.** Let us understand these points in a bit more detail.

Critical points in a curve are the points where the first derivative is equal to zero. They can be further divided into three points:

1.  **Maxima:** The point where the function attains the maximum value. Take a look at the point of maxima as shown in the image below:
    
    ![Point of Maxima](https://i.ibb.co/VqsV1Q4/Point-of-Maxima.png)
    
2.  **Minima:** The point where the function attains the minimum value. Take a look at the point of minima as shown in the image below:
    
    ![Point of Minima](https://i.ibb.co/g7Y5WqJ/Point-of-Minima.png)
    
3.  **Saddle Point:** The point where the function has minimum value with respect to one direction and maximum value with respect to the other direction. Take a look at the saddle point as shown in the image below. If you move along the horizontal axis from -4 to 4, you will conclude that the critical point (0,0) is a minima. And on the other hand, if you move along the other axis from -2 to 2, you'll conclude that the same critical point (0,0) is a maxima. Such a critical point is known as a Saddle Point. It got the name Saddle point because it looks very similar to horse saddle.
    
    ![Saddle Point](https://i.ibb.co/p1KCZm9/Saddle-Point.jpg)
    

There is something interesting to note here. What do you think is more beneficial for a learning algorithm like gradient descent, finding a local minima or a saddle point? The answer is saddle point as in the case of a saddle point, you at least have one direction where you can move towards the global minima. But, if you reach a local minima, you can get stuck in that minima and getting out if requires some modifications to the simple Stochastic Gradient Descent, which you'll see in the next few segments.

You also saw that the points of maxima and minima can be either local or global. A **local maxima/minima** are the maximum/minimum value in a certain **locality**. However, **global maxima/minima** are the maximum/minimum value or the **entire curve.**

Let us say you have a function that can be denoted by $f(x,y)$. A point will be a critical point if the following holds true:
$$\large{f_x=\dfrac{\delta\\f(x,~y)}{\delta\\x}=0\text{ and }f_y=\dfrac{\delta\\f(x,~y)}{\delta\\y}=0}$$

In order to compute maxima, minima and saddle points, you will require the following:
$$\large{H=f_{xx}.f_{yy}−f^2_{xy}}$$

Where,
$$\large{f_{xx}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\x}},$$
$$\large{f_{yy}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\y}\right)}{\delta\\y}}\text{ and},$$
$$\large{f_{xy}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\y}}$$

To compute the points, the following must stand true:

1.  The point $x$ will be a point of maxima if $H>0$ and $f''_{xx}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\x}<0$.  
     
2.  The point $x$ will be the point of minima if $H>0$ and $f''_{xx}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\x}>0$.  
     
3.  The point will be a saddle point if $H<0$

Now that you have an understanding of these points, let us solve them in the next video.

**VIDEO**

Let us revise the equation that you solved in the video above. You are required to compute all the possible maxima, minima and saddle points in the given equation:
$$\large{f(x,y)=3x^3+3y^3−6xy}$$

Let us start by computing fx, fy, fxx, fyy, fxy as shown below:

- $f_x=\dfrac{\delta\\f}{\delta\\x}=9x^2−6y$
- $f_y=\dfrac{\delta\\f}{\delta\\xy}=9y^2−6x$

Recall that for a critical point both fx and fy should be equal to zero. Let us substitute these equations equal to zero as shown below:
$$\large{9x^2−6y=0}$$$$\large{\therefore~y=\dfrac{3x^2}{2}}$$
$$\large{\text{and }9y^2−6x=0}$$

Substituting the value of y obtained above, you get: $9\left(\dfrac{3x^2}{2}\right)^2−6x=0$

On solving you will get:  $\dfrac{27x^4}{4}−2x=0$

$27x^4−8x=0$

$x(27x^3−8)=0$

$(x−0)((3x)^3−2^3)=0$

You will obtain the following values of $x$: $x=0,~x=\dfrac{2}{3}$

The corresponding y values: $y=0,~y=\dfrac{2}{3}$ respectively.

Therefore, you have the two critical points i.e., $(0,~0)$ and $\left(\dfrac{2}{3},~\dfrac{2}{3}\right)$.

Now, let us compute the value of $H$ and find the points of maxima, minima and saddle points:
$$f_{xx}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\x}=\dfrac{\delta\left(\dfrac{\delta\\(3x^3+3y^3-6xy)}{\delta\\x}\right)}{\delta\\x}=\dfrac{\delta(9x^2-6y)}{\delta\\x}=18x$$
$$f_{yy}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\y}\right)}{\delta\\y}=\dfrac{\delta\left(\dfrac{\delta\\(3x^3+3y^3-6xy)}{\delta\\y}\right)}{\delta\\y}=\dfrac{\delta(9y^2-6x)}{\delta\\y}=18y$$
$$\large{f_{xy}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\y}}=\dfrac{\delta\left(\dfrac{\delta\\(3x^3+3y^3-6xy)}{\delta\\x}\right)}{\delta\\y}=\dfrac{\delta(9x^2-6y)}{\delta\\x}=6$$

Substitute the values of  $f_{xx}$, $f_{yy}$ and $f_{xy}$ in the formula to compute H as follows:
$$\large{H=f_{xx}*f_{yy}−f^2_{xy}}$$
$$\large{H=18x∗18y−(6)^2=18x∗18y−36}$$
 
Let us check whether the critical points are maxima/minima or saddle points as shown below:

-   For the critical point $(0,~0)$, you will get the following:  $H(0,~0)=(18∗0)∗(18∗0)−36=−36<0$  
    According to the rules you learnt above, if $H<0$, this means $(0,~0)$ is a saddle point.  
     
-   For the critical point $\left(\dfrac{2}{3},~\dfrac{2}{3}\right)$, you will get the following value: $H(0,~0)=\left(18∗\dfrac{2}{3}\right)∗\left(18∗\dfrac{2}{3}\right)−36=144−36=108>0$  
    According to the rules you learnt above, if $H>0$, this means $\left(\dfrac{2}{3},~\dfrac{2}{3}\right)$ is either a point of maxima or minima.  
     
-   You can find whether it is a point of maxima or minima as follows:  
    $f''_{xx}(x,~y)=\dfrac{\delta\left(\dfrac{\delta\\f(x,~y)}{\delta\\x}\right)}{\delta\\x}=\dfrac{\delta\left(\dfrac{\delta\\(3x^3+3y^3-6xy)}{\delta\\x}\right)}{\delta\\x}=\dfrac{\delta(9x^2-6y)}{\delta\\x}=18x=18*\dfrac{2}{3}=12$  
    Since the result is greater than zero, it is a point of minima.

You have finally obtained the results for the equation $f(x,y)=3x^3+3y^3−6xy$. Let us conclude the results.

1. $(0,~0)$ is a saddle point.
2. $\left(\dfrac{2}{3},~\dfrac{2}{3}\right)$ is the point of minima.

In the upcoming segment, you will learn about the first gradient descent optimiser i.e., **momentum-based methods.**