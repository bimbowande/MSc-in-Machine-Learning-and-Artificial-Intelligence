# Regularization Techniques

In this segment, you will learn about some best practices and practical aspects of training neural networks. 

  
Neural networks are usually large, complex models with tens of thousands of parameters; thus, they have a tendency to **overfit** the training data, usually when the training data is less. As with many other ML models, **regularization** is a common technique used in neural networks to address this problem. Let’s quickly revise the concept of regularization in the upcoming video.

**VIDEO**

To summarise, one common regularization technique is to add a **regularization term** to the objective function. This term ensures that the model does not capture the 'noise' in the data set, i.e., it does not overfit the training data. This, in turn, leads to better **generalizability** of the model.

  
Let’s elaborate a bit on the generalizability of the model before proceeding further. Whenever you build and train any ML or DL model, the aim is to have a model that can accurately predict results on unseen data. Additionally, you would also want your model to have minimal error.

  
A model trained on the training data set tends to adapt to the data set, leading to overfitting, which means that the model is performing better on the training data set; however, it might not get a good result on unseen data, the test data. This leads to a lack of generalizability of the model. However, the training error of the model for such a case will be low and vice versa. 

  
Therefore, your model needs to strike a balance between controlling the training error and having good generalizability, which can be done using **regularization techniques.**

  
There are different types of regularization techniques, and the one discussed above can be represented in a general form as follows: 
$$\large{\text{Objective function}=\text{Loss function (Error term)}+\text{Regularization term}}$$

When you increase the regularization term, you are giving more value to the regularization terms which in turn leads to reducing the weight values (as the regularization term is a function of weights) as you need to keep the overall loss low. This ensures that the weights don't blow out of proportion.

Biases are not included in the regularization term. Why does this happen?

Let us take a neural network with linear activation for understanding this concept. Suppose the hidden layer under consideration has 1 neuron, it can be represented as follows:
$$\large{h=z=w.x+b}$$

where x is the input, w is the weight associated with the connection, $b$ is the bias, $z$ is the cumulative input and h is the output of the hidden layer.

The above equation mimics the equation of the line with $w$ as the slope and $b$ as the intercept. The product of slope and the input(independent variable) is added to the bias. Regularization smoothens this slope in order for it to not overfit on the input. The bias, however, is the intercept of this equation and does not have a direct effect on overfitting.

There are two important terms to keep in mind, which are as follows:

1.  **Bias:**
    1.  The bias of a model represents the amount of error that the model will commit on a given training data set, which essentially is a measure of the assumptions made by the model about the trends in the training data.  
         
    2.  If the assumptions made are a lot, take, for example, linear regression, the bias is high as the training error is high.
        1.  As you include more variables in the linear regression model, some 2nd or 3rd order variable, you are reducing the assumptions you are making about the model, hence, the training error decreases and the bias decreases.  
             
        2.  But, there is always a chance for this new linear regression model to overfit and have high variance.  
             
    3.  The same goes for deep learning models, however, the number of assumptions in the case of deep learning model is much less than that in linear regression.  
         
    4.  Bias quantifies **how accurate** the model is likely to be on the **future/ test data**.  
         
2.  **Variance:**
    1.  The variance of the model measures to what extent the model changes when trained on a different data set.  
         
    2.  So, if the variation in the model parameters is a lot when you train the model on different subsets of training data, it means that the model has high variance.  
         
    3.  In other words, the ‘variance’ of a model is the variance in its output on the same test data with respect to the changes in the training data. It is the degree of changes in the model itself with respect to changes in training data.

Hence, as you increase the regularization parameter, you are forcing the weight values to go close to zero, making the model simpler, essentially reducing the variance. Regularization by making the model simple ensures that the model does not learn very minute patterns like noise, which in turns causes the bias to increase.

Answer the following questions to test your understanding of the concepts covered in this segment.

#### Regularization

Qn: What happens when we try to reduce the value of the loss function?

- Variance decreases

- Bias decreases

- Bias increases

Ans: B. *As we lower the loss function, which is a measure of error, we make the model learn more, which reduces the bias. The variance will likely increase as there is a high chance of overfitting.*

Qn: What happens when we increase the value of the regularization term? (Note: More than one option may be correct.)

- Variance decreases

- Variance increases

- Bias decreases

- Bias increases

- The model overfits

Ans: 

Let’s explore the different types of regularization techniques used in neural networks. This is something you must have studied earlier in regression. Recall that L1 and L2 regularization (also called ridge and lasso regression in the context of linear regression) is commonly used to regularize regression models. The same idea can be extended to neural networks. Let’s watch the next video to learn more about this.

**VIDEO**

The objective function can be written as:

$$\large{\text{Objective function}=L(F(x_i),~\theta)+\lambda\\f(\theta)}$$

where $L(F(x_i),~\theta)$ is the loss function expressed in terms of the model output F(xi) and the model parameters θ. The second term $\lambda\\f(\theta)$ has two components -  the **regularization parameter** λ and the **parameter norm** $f(\theta)$.

There are broadly two types of regularization techniques followed in neural networks:

1. L1 norm: $\lambda\\f(\theta)=||\theta||_1$ is the sum of all the model parameters

2. L2 norm: $\lambda\\f(\theta)=||\theta||_2$ is the sum of squares of all the model parameters

Note that you consider only the weights (and not the biases) in the norm since trying to regularize bias terms has empirically proven to be counterproductive for performance.

The 'parameter norm' regularisation that we have just discussed is similar to what you had studied in linear regression in almost every aspect. As in **lasso regression** (L1 norm), we get a **sparse weight matrix**, which is not the case with the L2 norm. Despite this fact, the L2 norm is more common because the sum of the squares term is easily **differentiable** which comes in handy during backpropagation.

Let us look a bit more into the differentiability aspect of the two techniques:

1.  L1 norm is the sum of model parameters i.e., a linear function. It can be represented graphically as follows:
    
    ![L1 Normalization](https://i.ibb.co/0V37D72/L1-Normalization.png)  
    Let us take a single weight element and linear activation to understand the concept. You can mathematically write the output as: $h=z=w.x+b$. The L1 norm for this equation can be written as $L1=|w|$.  
      
    The differential of this function with respect to the weight will be: ∂L∂w=∂|w|∂w.  This can be broken down as follows:  
    $$\large{\dfrac{\delta\\L}{\delta\\W}=1~\text{for}~w>0~\text{and}~\dfrac{\delta\\L}{\delta\\W}=−1~\text{for}~w<0}$$  
      
    However, at 0, this function will not be defined and hence **not be differentiable.**  
     
    
2.  L2 norm is the sum of squares of model parameters. It can be represented as follows:
    
    ![L2 Normalization](https://i.ibb.co/QD0BS6X/L2-Normalization.png)  
    For output: $h=z=w.x+b$, the L2 norm can be written as $L2=w^2$. The differential of this function with respect to the weight will be: $\dfrac{\delta\\L}{\delta\\W}=\dfrac{\delta\\w^2}{\delta\\W}=2w$ for all values of w. This function is differentiable at all points including zero.
    

Try to solve the following questions.

#### L1 Norm

Qn: In a two-layer network with one hidden layer, you have the following weight matrices and the bias vectors:
$$\large{w^1=\begin{bmatrix}w^1_{11}&w^1_{12}\\w^1_{21}&w^1_{22}\end{bmatrix},~b^1=\begin{bmatrix}b^1_1\\b^1_2\end{bmatrix},~w^2=\begin{bmatrix}w^2_{11}&w^2_{12}\\w^2_{21}&w^2_{22}\end{bmatrix}~\text{and},~b^2=\begin{bmatrix}b^2_1\\b^2_2\end{bmatrix}}$$

What will be the expression of the norm, considering you are using the L1 norm?

- $absolute(w^1_{11}+w^1_{12}+w^1_{21}+w^1_{22}+w^2_{11}+w^2_{12}+w^2_{21}+w^2_{22}+b^1_1+b^1_1+b^1_2+b^2_1+b^2_2)$

- $absolute(w^1_{11}+w^1_{12}+w^1_{21}+w^1_{22}+w^2_{11}+w^2_{12}+w^2_{21}+w^2_{22})$

Ans: B. *Use the following formula to obtain the results: L1 norm: $\lambda\\f(\theta)=||\theta||_1$ is the sum of all the model parameters. Also, recall that biases are not included in the expression of the norm.*

#### L2 Norm

In a two-layer network with one hidden layer, you have the following weight matrices and the bias vectors:
$$\large{w^1=\begin{bmatrix}w^1_{11}&w^1_{12}\\w^1_{21}&w^1_{22}\end{bmatrix},~b^1=\begin{bmatrix}b^1_1\\b^1_2\end{bmatrix},~w^2=\begin{bmatrix}w^2_{11}&w^2_{12}\\w^2_{21}&w^2_{22}\end{bmatrix}~\text{and},~b^2=\begin{bmatrix}b^2_1\\b^2_2\end{bmatrix}}$$

What will be the expression of the norm, considering you are using the L2 norm?

- $(w^1_{11}+w^1_{12}+w^1_{21}+w^1_{22}+w^2_{11}+w^2_{12}+w^2_{21}+w^2_{22}+b^1_1+b^1_1+b^1_2+b^2_1+b^2_2)^2$

- $(w^1_{11})^2+(w^1_{12})^2+(w^1_{21})^2+(w^1_{22})^2+(w^2_{11})^2+(w^2_{12})^2+(w^2_{21})^2+(w^2_{22})^2+(b^1_1)^2+(b^1_1)^2+(b^1_2)^2+(b^2_1)^2+(b^2_2)^2$

- $(w^1_{11}+w^1_{12}+w^1_{21}+w^1_{22}+w^2_{11}+w^2_{12}+w^2_{21}+w^2_{22})^2$

- $(w^1_{11})^2+(w^1_{12})^2+(w^1_{21})^2+(w^1_{22})^2+(w^2_{11})^2+(w^2_{12})^2+(w^2_{21})^2+(w^2_{22})^2$

Ans: D. *Use the following formula to obtain the results: L2 norm: $\lambda\\f(\theta)=||\theta||_2$ is the sum of squares of all the model parameters. Also, recall that biases are not included in the expression of the norm.*

Apart from using the parameter norm, there is another popular neural network regularization technique called **dropouts**. Let’s proceed to the next segment to learn how this technique works.