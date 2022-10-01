# Gradient Descent

As you learnt in the previous segment, training refers to the task of finding the optimal combination of weights and biases to minimise the total loss (with a fixed set of hyperparameters). In this segment, you will learn about the anatomy and complexity of the cost function and how to find the optimal parameters.

  
The optimisation is done using the **gradient descent** algorithm. You have already been introduced to this algorithm in the machine learning modules. Let’s recall the algorithm and how it works for optimising deep neural networks.

**VIDEO**

Gradient descent is an optimisation algorithm used to find the minimum value of a function. The basic idea is to use the gradient of the function to find the direction of the steepest descent, i.e., the direction in which the value of the function decreases most rapidly, and move towards the minima iteratively according to the following rule:
$$\large{w_{new}=w_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w}}$$
The same can be written for biases as follows:
$$\large{b_{new}=b_{old}−\alpha*\dfrac{\delta\\L}{\delta\\b}}$$
With the gradient descent algorithm, your model will keep on updating the weights and biases iteratively until the **point of convergence** is reached. The point of convergence is a point where your parameters will obtain optimal value. For example, at the point of convergence, the weight values obtained for different iterations will be approximately equal to each other. Therefore, indicating that the weights have reached the optimal value and updating them further will not bring about any more improvement. This is usually the minima in most cases but in cases when the loss function is really complex, reaching the global minima becomes difficult and you get stuck at the local minima.

Another interesting thing to notice here is that while trying to optimising the parameters using the gradient descent algorithm, you are trying to reach the minima as shown in the image below:

![Gradient Descent 1](https://i.ibb.co/SwMsJR8/Gradient-Descent-1.png)

This is done because our aim is to minimise the overall loss/cost of the model by updating the values of parameters(weights and biases). The −α term which is being multiplied to the gradient $\dfrac{\delta\\L}{\delta\\w}$ or $\dfrac{\delta\\L}{\delta\\b}$ ensures that the iterations move towards the negative value until the point of convergence is reached.

The learning rate α is a **hyperparameter** that can take any value as specified by the user while writing the code. This hyperparameter defines how fast the values move towards the minima of the curve. The values of the learning rate usually lie between 0 to 1. This is because very small or very large values might not work to your advantage. Let’s try to understand why this happens with the following points:

1.  If the learning rate is too small, it will take a very long time to reach the minima, as each step size is very small as shown below.
    
    ![Gradient Descent 2](https://i.ibb.co/4VsZszw/Gradient-Descent-2.jpg)
    
    Where $J(\theta)$ is the cost of the model with $\theta$ parameters.  
     
    
2.  If the learning rate is optimal, your function will take certain steps that are neither too small nor too large and reach the point of minima.
    
    ![Gradient Descent 3](https://i.ibb.co/26zvdcq/Gradient-Descent-3.jpg)
    
3.  If the learning rate is very large, your function will take very large jumps and might never reach the point of minima.
    
    ![Gradient Descent 4](https://i.ibb.co/GRRs1yd/Gradient-Descent-4.jpg)
    

You must have realised by now that the learning rate is a very important hyperparameter. The number of steps you take to reach the minima is the number of **iterations** that you run the gradient descent algorithm. As the number of iterations increase, the training time increases. Hence, you need to find an optimal value for the same.

Let’s take a look at a few examples of different functions and understand how the gradient descent algorithm works.

**Example 1:** Let's consider a one-dimensional (univariate) function. Suppose you have a loss function L, which depends only on one variable w. For simplicity, let's consider $L(w)=w^2$. The minimum value of this function is at $w=0$, as shown below.

![Gradient Descent 5](https://i.ibb.co/7SKkZvy/Gradient-Descent-5.png)

The algorithm starts with an initial arbitrary guess of w, computes the gradient at that point, and updates w iteratively using the formula. Let's take an arbitrary initial value w0=5 and apply it to the following formula: 
$$\large{Gradient=\dfrac{\delta\\L}{\delta\\w}=\dfrac{\delta(w^2)}{\delta\\w}=2w}$$
You are given $w_0=5$; hence, the gradient (the slope) at $w_0$ is $2∗5=10$

The gradient has two critical pieces of information, which are as follows:

-   The **sign of the gradient** (positive here) is the 'direction' in which the function value increases, and thus, the negative value of that sign is the **direction** in which the **function value decreases.** If you move up in the direction of the gradient, you can see that the value of w increases and you move away from the minima which is at $w=0$. Hence, you move down, i.e, the negative direction of the gradient.  
     
-   The **value of the gradient** (10 here) represents how steeply the function value increases or decreases at that point.

You want to move in the direction of the decreasing function value, i.e., in the negative direction of the gradient (towards the origin from $w_0=5$). Also, you want to take a larger step if the gradient value is high, and a smaller step if the gradient value is low. You need to control the **step size** through the **learning rate $\large\alpha$**. Both these ideas are captured in the term $−\alpha*\dfrac{\delta\\L}{\delta\\w}$.

Let's perform one iteration of the gradient descent starting with $w_0=5$ and $\alpha=0.1$.
$$\large{w_0(new)=w_0−\alpha*\dfrac{\delta\\L}{\delta\\w}}$$$$\large{w_0(new)=5−(0.1)*(10)=4}$$
Notice that you have moved closer to the minima. Try to perform another iteration to verify whether you move closer or not.

#### Gradient Descent

Qn: Consider the minimisation of the univariate function $L(w)=w^2$. You have already seen one iteration starting with $w_0=5$, which moves to $w_1=4$. Perform one more iteration with the same learning rate $\alpha=0.1$. What is the value of $w_2$?

- 4.8

- 3.2

- 3.6

Ans: B. *Calculate the second iteration as follows:*

$w_2=w_1−\alpha*\dfrac{\delta\\L}{\delta\\w}=w_1−\alpha*2w=4−0.1∗8=3.2$


**Example 2:** Gradient descent can be easily extended to multivariate functions, i.e., functions of multiple variables. Let's take the bivariate function $L(w_1,~w_2)=w^2_1+w^2_2$. The minimum value of this function is 0 at the point $(w_1,~w_2)=(0,~0)$. For convenience, let's represent the two variables together as $W=(w_1,~w_2)$, as shown in the graph below.

![Gradient Descent 6](https://i.ibb.co/ts0kS3C/Gradient-Descent-6.png)

In this example, instead of having a single value of $\dfrac{\delta\\L}{\delta\\w}$, you will have an $n$-dimensional vector of $\dfrac{\delta\\L}{\delta\\w}$. Here, $n=2$. Therefore, you will have the following values:
$$\large{\dfrac{\delta\\L}{\delta\\w}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\w_1}\\\dfrac{\delta\\L}{\delta\\w_2}\end{bmatrix}=\begin{bmatrix}2w_1\\2w_2\end{bmatrix}}$$

**Note** that w1, w2 are independent of each other. Hence, $\dfrac{\delta\\w_2}{\delta\\w_1}$, $\dfrac{\delta\\w_1}{\delta\\w_2}$ are equal to 0.

Each component of the **gradient vector** conveys the same two pieces of information. For e.g.

let's take an initial guess $W_0=(5,~−4)$. The gradient at this point is:
$$\large{\dfrac{\delta\\L}{\delta\\w}=\begin{bmatrix}2w_1\\2w_2\end{bmatrix}=\begin{bmatrix}10\\-8\end{bmatrix}}$$

The first component $(2w_1=10)$, being positive, says that the function value increases along the direction of increasing $w_1$, and the 'rate of change' along the $w_1$ axis is 10. Similarly, the second component $(2w_2=−8)$ says that the function decreases along the direction of increasing $w_2$ with a rate of 8.

Combing both the elements, the **negative of the gradient vector**, $-\begin{bmatrix}2w_1\\2w_2\end{bmatrix}=\begin{bmatrix}10\\-8\end{bmatrix}$, is the **direction** in which the function value decreases most rapidly. The gradient vector is shown on a $w_1-w_2$ plane below:

![Gradient Descent 7](https://i.ibb.co/X3cKt3F/Gradient-Descent-7.jpg)

We take a step along that vector according to (assuming the same learning rate $\alpha=0.1$):
$$\large{W_1=W_0−\alpha*\dfrac{\delta\\L}{\delta\\w}}$$
$$\large{W_1=\begin{bmatrix}5\\−4\end{bmatrix}−0.1\begin{bmatrix}10\\−8\end{bmatrix}}$$
$$\large{W_1=\begin{bmatrix}4\\−3.2\end{bmatrix}}$$

Notice that the point $\large{W_1=\begin{bmatrix}4\\−3.2\end{bmatrix}}$ is closer to the minima (0,0) than the starting point $W_0=\begin{bmatrix}5\\−4\end{bmatrix}−0.1\begin{bmatrix}10\\−8\end{bmatrix}$. How to verify this mathematically? Use the distance rule of coordinate geometry. For $W_0=\begin{bmatrix}5\\−4\end{bmatrix}−0.1\begin{bmatrix}10\\−8\end{bmatrix}$, distance = $\sqrt{(5−0)^2+(−4−0)^2}=\sqrt{41}$ and for $\large{W_1=\begin{bmatrix}4\\−3.2\end{bmatrix}}$, distance = $\sqrt{(4−0)^2+(−3.2−0)^2}=\sqrt{26.24}$.

Perform one more iteration from $W_1$ to $W_2$ and verify that you move closer to the minima.

You can now extend this idea to any number of variables. Suppose one of the neural network layers has n biases. You can represent them in a large vector $(b_1,~b_2,\dots\\b_n)$. In this case, the gradient vector will also be an n-dimensional vector, each element of which captures two pieces of information, the direction and the rate of change of the function with respect to the parameter bi. The gradient of the loss with respect to the bias is shown below:
$$\large{\dfrac{\delta\\L}{\delta\\b}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\b_1}\\\dfrac{\delta\\L}{\delta\\b_2}\\\dots\\\dots\\\dfrac{\delta\\L}{\delta\\b_n}\end{bmatrix}}$$

Try answering the following questions:

#### Gradient Descent

Qn: Consider an n-dimensional setting where the loss function L depends on n parameters. Choose all correct statements about the gradient of the loss function with respect to the model parameters, from below.

- The gradient is an n-dimensional vector.

- The gradient is a scalar.

- The gradient is the direction in which the loss value decreases most rapidly.

- The gradient is the direction in which the loss value increases most rapidly.

Ans: A & D. *The gradient of a function is an n-dimensional vector. The gradient vector is the direction in which the loss value increases most rapidly.*

#### Gradient of a Loss with Respect to Multiple Variables

Qn: Suppose a layer in your neural network has a large number of biases, n biases, denoted by the variable b. In some iteration of the algorithm, the gradient is computed to be as follows:
$$\large{\dfrac{\delta\\L}{\delta\\b}=\begin{bmatrix}\dfrac{\delta\\L}{\delta\\b_1}\\\dfrac{\delta\\L}{\delta\\b_2}\\\dots\\\dfrac{\delta\\L}{\delta\\b_j}\\\dfrac{\delta\\L}{\delta\\b_{j+1}}\\\dfrac{\delta\\L}{\delta\\b_{j+2}}\\\dots\\\dfrac{\delta\\L}{\delta\\b_n}\end{bmatrix}}=\begin{bmatrix}0.45\\-0.30\\\dots\\\dfrac{\delta\\L}{\delta\\b_j}\\0.20\\0.00\\\dots\\\dfrac{\delta\\L}{\delta\\b_n}\end{bmatrix}$$
Now, imagine an n-dimensional space whose each dimension (axis) corresponds to one parameter of the network. Considering this scenario, select all the correct statements from below.

- In the next iteration, the algorithm should move in the direction of the decreasing $b_1$ value.

- In the next iteration, the algorithm should move in the direction of the increasing $b_1$ value.

- In the next iteration, the algorithm should move towards the increasing $b_2$ value.

- In the next iteration, the algorithm will take a larger step along the dimension $b_1$ than $b_2$.

- In the next iteration, the algorithm will take a larger step along the dimension $b_2$ than $b_1$.

- Changing $b_{j+2}$ slightly does not affect the value of the current loss significantly.

Ans: A, C, D, & F. *The loss with respect to b increases if $\dfrac{\delta\\L}{\delta\\b}$ is positive (and vice versa). If it is zero, it means that the loss does not depend (locally) on that variable. Also, the magnitude of the gradient defines how large a step the algorithm takes along that variable.*

Now that you have learnt about gradient descent and optimising model parameters, let’s proceed to the next segment to solve an interesting comprehension on model training.