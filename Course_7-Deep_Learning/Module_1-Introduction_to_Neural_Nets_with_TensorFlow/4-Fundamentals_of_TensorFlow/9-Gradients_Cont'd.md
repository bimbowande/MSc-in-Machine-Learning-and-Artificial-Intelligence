# Gradients (Cont'd)

In the previous segment, you saw that GradientTape() can be used to find the derivatives of a dependent variable with respect to an independent variable. Now, you can also use gradient tape to find the values of partial derivatives. The method is similar to the one you saw in the previous segment; the only differences are the equations and the variables. Now, in the forthcoming video, you will see an example of partial derivatives.

**VIDEO**

So, as you saw in the video, by simply changing the variables in the gradient tape context, you can obtain the values of the partial derivatives. In the video, Avishek also discussed a couple of other capabilities of gradient tape. Let us discuss each of these capabilities one by one: 

1.  **Chain rule:** In a function representing $y=h(x)$, in which x is defined as $x=g(r)$, you can calculate $\dfrac{dy}{dr}$ directly. Gradient tape can calculate the gradient based on the chain rule independently, without you having to specify the internal dependencies. To brush up on the chain rule, you can visit the optional module on ‘Math for Machine Learning’ in the course ‘Machine Learning I’.   
     
2.  **Persistence of variables:** Consider a system of the following equations:  
    $p=a(x);~q=b(p);~y=c(q);$
    After defining all the equations inside the gradient tape, all the intermediate variables inside the tape, such as p and q, will be lost. You can use the chain rule to calculate the derivative of y with respect to $q$, $p$ or $x$. However, it is not possible to calculate $\dfrac{dq}{dx}$ unless you mention the parameter ‘persistent = True’ in the gradient tape. 

**VIDEO**

There is one more property of gradient tape that might prove useful later: You can control whether a variable can be trainable or not. In the next video, you will learn how to control the trainable state of a variable.

**VIDEO**

By simply making variables non-trainable, you can prevent them from being used for calculating gradients.

So, here is a list of the fundamental mathematical capabilities of TensorFlow, which are important for ML tasks: 

1.  Declaring tensors 
2.  Conducting basic mathematical operations 
3.  Performing linear algebra tasks using tensors 
4.  Reshaping and broadcasting tensors 
5.  Computing auto-gradient using TensorFlow

Try answering the following questions:

#### Partial Derivatives

Consider the set of equations given below. 

$\large{t=\sqrt{x^{0.3}+0.1}}$

$\large{p=e^{4t}}$

$\large{q=p^2−4p}$

What is the derivative of p and q with respect to x at x = 5?

- 40.12; 39657.12

- 28.15; 10577.51

- 21.59; 52148.35

- 15.84; 37598.25

Ans: B. *By setting the parameter ‘persistence = true’, all the intermediate equations will be stored in the tape that can be called later. The following code segment will help you with the same:*

```python
x = tf.Variable([5.0], dtype=float)
C1 = tf.constant([4], dtype= float)

with tf.GradientTape(persistent= True) as tape:
 t = tf.math.sqrt(tf.pow(x,0.3)+0.1)
 p = tf.pow (2.718, C1*t)
 q = tf.pow(p,2) - C1*p

dp_dx = tape.gradient(p,x)
dq_dx = tape.gradient(q,x)

print("dp/dx = ", dp_dx.numpy()[0])
print("dq/dx = ", dq_dx.numpy()[0])
```

Moving ahead, in the next segment, you will apply the differentiation technique to minimise a function. But before that, answer these questions based on your learning from this segment.