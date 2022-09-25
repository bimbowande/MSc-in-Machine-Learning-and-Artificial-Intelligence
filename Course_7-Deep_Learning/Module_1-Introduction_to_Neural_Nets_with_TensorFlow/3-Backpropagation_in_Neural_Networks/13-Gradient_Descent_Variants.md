# Gradient Descent Variants

So far, you have used batch gradient descent by calculating the gradients for the entire data set and updating the parameters. In order to deal with batches of data points, you need to have a good understanding of the other variants of this algorithm, which are as follows:

1.  Stochastic gradient descent 
2.  Mini-batch gradient descent 

In batch gradient descent, you update the weights only after you do feed-forward of all the data points in the batch/ dataset. These variants will enable you to update the weights and biases multiple times during one pass through all the data points in the dataset. Let’s watch the next video to learn about these three variants one by one.

**VIDEO**

Some of the important points regarding these three variants can be summarised as follows:

1.  **Batch gradient descent**:
    1.  It is also referred to as 'vanilla gradient descent'.
    2.  This algorithm takes into account the entire training data set and calculates the gradient for all the points in it before updating the weights and biases. Hence, the batch size = n, where 'n' is the total number of data points in the dataset.
    3.  Due to this, the number of points required in memory becomes very large.
    4.  Also, the time required for calculating the gradient for the entire training set increases significantly as the matrix dimensions increase with the increase in data points.  
         
2.  **Stochastic gradient descent**:
    1.  This algorithm does the feedforward of a single data point, backpropagates the errors and updates the weight and biases. Hence, the parameter updates happen after every data point is fed to the network. Hence, the batch size here = 1.
    2.  It requires much less memory as compared to batch gradient descent. This is because only a certain training set is required in the memory at a particular point in time.
    3.  Since updates are made after calculating the gradient of each training set, it requires frequent updates.
    4.  Also, since you are using a single point's gradient to make updates, there is a high chance that the direction that you move may not be the correct direction, i.e,  towards the minimum.  
         
3.  **Mini-batch gradient descent**:
    1.  This algorithm divides the training set into batches and calculates the gradient of all the points in that particular batch before updating the weights and biases. Hence, the batch size < n, where 'n' is the total number of data points in the dataset.
    2.  Since the number of points in a batch is less than that in the entire training set, it requires less memory than the batch gradient descent algorithm but more than that required by the stochastic gradient descent algorithm. 
    3.  This is a widely used method, as it strikes a balance between the previous two methods.

Now that you are familiar with the three variants, let’s watch the next video to understand the algorithm for them.

**VIDEO**

Let’s take a look at the following algorithm:

1. Batch size $=m$
2. For each epoch in $[1,~2,\dots, L]$:
    1. Reshuffle the data set
    2. Number of batch $=\dfrac{n}{m}$
    3. For each batch in $[1,~2,\dots,~number~of~batch]$:
        1. Compute the gradient for each input in the batch $[batch_{i−1}∗m,~batch_i∗m]$
    4. Average gradient $\nabla\\W$ = Sum of gradient $\nabla\\W$ / $m$
    5. Average gradient $\nabla\\W$ = Sum of gradient $\nabla\\b$ / $m$
    6. $W=W-\nabla\\W,~b=b-\nabla\\b$

This algorithm can be used for any of the variants based on the value of n (total number of datapoints), in the following ways:

1.  If the $m=1$, number of batches $=\dfrac{n}{m}$ will be equal to $n$ ie., the number of batches will be equal to the number of datapoints. Therefore, the algorithm used will be stochastic gradient descent.  
     
2.  If $m=n$, number of batches $=\dfrac{n}{m}$ will be equal to 1. Therefore, the algorithm used will be batch gradient descent.  
     
3.  If $1<m<n$, number of batches $=\dfrac{n}{m}$ will lie between 1 to $n$. Therefore, the algorithm used will be mini-batch gradient descent.

Now try to answer the following questions.

#### Number of Batches

Qn: Consider a data set of 1,00,000 data points. Now, you decide to perform mini-batch/ stochastic gradient descent with a batch size of 50. How many batches can this data set be segmented/processed into?

- 1,00,000

- 1

- 2000

Ans: C. *The number of batches can be calculated as follows:  Number of batches $=n/m=1,00,000/50=2,000$*

#### Number of Updates

Qn: Consider a data set of 1,00,000 data points. Now, you decide to perform mini-batch/ stochastic gradient descent with a batch size of 50 for 3 epochs. How many updates will you make at the end of 3 epochs?

- 1

- 6000

- 2000

Ans: B. *You will need to make ‘Number of epochs X Number of mini-batches’ updates, which can be calculated as follows: $3*2,000=6,000$*

Now that you have a good understanding of this algorithm, let’s resume building and training your MNIST neural network. Let’s get started.