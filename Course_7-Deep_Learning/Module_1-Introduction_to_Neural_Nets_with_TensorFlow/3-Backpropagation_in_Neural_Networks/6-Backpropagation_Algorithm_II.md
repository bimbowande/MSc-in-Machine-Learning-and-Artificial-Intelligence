# Backpropagation Algorithm - II

In the previous segment, you saw a very simple neural network with no hidden layers and only one neuron in each layer. Using the example, you understood the working of the backpropagation algorithm. Now, before you derive the equations and write the pseudocode for a complex neural network, let’s take a look at another simplified example for better understanding.

**VIDEO**

Earlier, you solved an example without any hidden layers in the network. For this example, you will take a simple neural network with an input layer, an output layer and two hidden layers. Also, the network will have zero bias and linear activation for simplicity. Take a look at the network given below. You can see that all the terms $x,~w^{[1]},~y^{[1]},~w^{[2]},~y^{[2]},~w^{[3]}~and~y^{[3]}$ are of the dimensions (1, 1). This makes differentiation very easy for us. You'll see later how to do the backpropagation when the dimensions are of the order (x, y) where x and y are greater than 1.

![Linear Network](https://i.ibb.co/vJssSXf/Linear-Network.png)

This example will help you develop a good understanding of the working of the chain rule, which forms an important part of this algorithm. Let’s start solving the problem step by step as follows:

1.  **Feedforward propagation:**
    1. $y^{[1]}=w^{[1]}*x$
    2. $y^{[2]}=w^{[2]}*y^{[1]}$
    3. $y^{[3]}=w^{[3]}*y^{[2]}$  
         
2.  **Loss computation:** 
    1. $MSE~loss=(y^{[3]}−y)^2$
         
3.  **Backpropagation:**
    1. $w^{[1]}_{new}=w^{[1]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w^{[1]}}$ where $\dfrac{\delta\\L}{\delta\\w^{[3]}}=\dfrac{\delta\\L}{\delta\\y^{[3]}}*\dfrac{\delta\\y^{[3]}}{\delta\\w^{[3]}}$
        \[You do not directly compute the partial derivative of L with respect to $w^{[3]}$, as L is not directly a function of $w^{[3]}$ a function of $y^{[3]}$, which is, in turn, a function of $w^{[3]}$. Therefore, using the chain rule, you can write the equation as shown above. Similarly, you can write the other equations as well. The chain rule simplifies the gradient calculations. ]  
         
    2. $w^{[2]}_{new}=w^{[2]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w^{[2]}}$ where $\dfrac{\delta\\L}{\delta\\w^{[2]}}=\dfrac{\delta\\L}{\delta\\y^{[3]}}*\dfrac{\delta\\y^{[3]}}{\delta\\y^{[2]}}*\dfrac{\delta\\y^{[2]}}{\delta\\w^{[2]}}$  
         
    3.  $w^{[3]}_{new}=w^{[3]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w^{[3]}}$ where $\dfrac{\delta\\L}{\delta\\w^{[1]}}=\dfrac{\delta\\L}{\delta\\y^{[3]}}*\dfrac{\delta\\y^{[3]}}{\delta\\y^{[2]}}*\dfrac{\delta\\y^{[2]}}{\delta\\y^{[1]}}*\dfrac{\delta\\y^{[1]}}{\delta\\w^{[1]}}$  
         
4.  These values of $\dfrac{\delta\\L}{\delta\\w^{[1]}}$, $\dfrac{\delta\\L}{\delta\\w^{[2]}}$ and $\dfrac{\delta\\L}{\delta\\w^{[3]}}$ can then be used to update the weights $w^{[1]}$, $w^{[2]}$ and $w^{[3]}$ using the gradient descent weight update equations.

Try computing the gradients using the equations you have derived above:

#### Updating Weights

Qn: What will be the value of **w[2]new** and **w[3]new** for this example? (Note: More than one option may be correct.)

- $w^{[2]}_{new}=w^{[2]}_{old}−\alpha*(2(y^{[3]}−y)∗w^{[3]}∗y^{[2]})$

- $w^{[3]}_new=w^{[3]}_{old}−\alpha*(2(y^{[3]}−y)∗y^{[2]})$

- $w^{[2]}_{new}=w^{[2]}_{old}−\alpha*(2(y^{[3]}−y)∗w^{[3]}∗y^{[1]})$

- $w^{[3]}_new=w^{[2]}_{old}−\alpha*(2(y^{[3]}−y)∗y^{[2]})$

Ans: B & C.

- *Solve the problem for the updated weights using the equations as follows:*
	1. $w^{[3]}_{new}=w^{[3]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w}$
	2. $w^{[3]}_{new}=w^{[3]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\y^{[3]}}*\dfrac{\delta\\y^{[3]}}{\delta\\w^{[3]}}$
	    
	    1. $\dfrac{\delta\\L}{\delta\\y^{[3]}}=2(y^{[3]}−y)$
	        
	    2. $\dfrac{\delta\\y^{[3]}}{\delta\\w^{[3]}}=y^{[2]}$
	        
	3. $w^{[3]}_{new}=w^{[3]}_{old}−\alpha*(2(y^{[3]}−y)∗y^{[2]})$

- Solve the problem for the updated weights using the equations as follows:
	1. $w^{[2]}_{new}=w^{[2]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w}$
	2. $w^{[3]}_{new}=w^{[3]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\y^{[3]}}*\dfrac{\delta\\y^{[3]}}{\delta\\y^{[2]}}*\dfrac{\delta\\y^{[2]}}{\delta\\w^{[2]}}$
	    
	    1. $\dfrac{\delta\\L}{\delta\\y^{[3]}}=2(y^{[3]}−y)$
	        
	    2. $\dfrac{\delta\\y^{[3]}}{\delta\\y^{[2]}}=w^{[3]}$
	        
	    3. $\dfrac{\delta\\y^{[2]}}{\delta\\w^{[2]}}=y^{[1]}$
	        
	3. $w^{[2]}_{new}=w^{[2]}_{old}−\alpha*(2(y^{[3]}−y)∗w^{[3]}∗y^{[1]})$

If you were unable to understand or correctly solve the above questions, do not worry! In the upcoming video, let us understand how to solve the gradient of  **w[1]** step by step:

**VIDEO**

Let’s update $w^{[1]}$ by substituting the values that you derived above as follows: 

1. $w^{[1]}_{new}=w^{[1]}_{old}−\alpha*\dfrac{\delta\\L}{\delta\\w^{[1]}}$
     
2.  Using the chain rule, you will get: $\dfrac{\delta\\L}{\delta\\w^{[1]}}=\dfrac{\delta\\L}{\delta\\y^{[3]}}*\dfrac{\delta\\y^{[3]}}{\delta\\y^{[2]}}*\dfrac{\delta\\y^{[2]}}{\delta\\y^{[1]}}*\dfrac{\delta\\y^{[1]}}{\delta\\w^{[1]}}$
    1. $\dfrac{\delta\\L}{\delta\\y^{[3]}}=\dfrac{\delta(y^{[3]}-y)^2}{\delta\\y^{[3]}}=2(y^{[3]}-y)$
    2. $\dfrac{\delta\\y^{[3]}}{\delta\\y^{[2]}}=\dfrac{\delta(w^{[3]}*y^{[2]})}{\delta\\y^{2}}=w^{[3]}$
    3. $\dfrac{\delta\\y^{[2]}}{\delta\\y^{[1]}}=\dfrac{\delta(w^{[2]}*y^{[1]})}{\delta\\y^{1}}=w^{[2]}$
    4. $\dfrac{\delta\\y^{[1]}}{\delta\\w^{[1]}}=\dfrac{\delta(w^{[1]}*x)}{\delta\\w^{1}}=x$  
         
3.  Therefore, $\dfrac{\delta\\L}{\delta\\w^{[1]}}=2(y^{[3]}−y)∗w^{[3]}∗w^{[2]}∗x$  
     
4.  You can substitute the value obtained above to the weight update equation and brain the following: $w^{[1]}_{new}=w^{[1]}_{old}−\alpha*(2(y^{[3]}−y)∗w^{[3]}∗w^{[2]}∗x)$

So far, you solved two simple neural networks and learnt how errors are backpropagated. In the upcoming segments, you will solve a much more complex network and write the pseudo-code for the same.
