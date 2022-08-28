# Change of Basis

By now, you may have gained a basic understanding of what PCA does. You have also been introduced to the concept of basis. Basis is defined as the fundamental set of vectors, the linear combination of which can represent any data point in that space. In this segment, you will  learn how to change the basis from the original to a new one. 

Does this seem like something you have already heard? Well, no. But you have seen something similar when you were getting an intuitive understanding of PCA where upon rotation of the axis, the covariance values diminished. This change of axis is known as the change of basis vectors. To understand this in detail, let’s consider the same dataset of height and weight. 

You have seen that the height and weight of a patient is 165 cm and 55 kg, respectively, which can be represented as 5.4 ft and 121.3 lbs, respectively, in the ft-lbs basis system. This does seem like a change of basis. Let’s watch the next video to understand this better.

**VIDEO**

As you know that 1 ft is equal to 30.48 cm and 1 lbs is equal to 0.45 kg, the height and weight of 165 cm and 55 kg, respectively, can be represented in the following format.

$$\begin{bmatrix}165\\55\end{bmatrix}=165\begin{bmatrix}1\\0\end{bmatrix}+55\begin{bmatrix}0\\1\end{bmatrix}=5.4\begin{bmatrix}30.48\\0\end{bmatrix}+121.3\begin{bmatrix}0\\0.45\end{bmatrix}$$

  
Where 165 cm will be equivalent to 5.4 ft and 55 kg is equivalent to 121.3 lbs. 

Let’s write the equation given above in a vector format.

You have a vector ‘v’ 

$v=\begin{bmatrix}165\\55\end{bmatrix}$

Where 

$\begin{bmatrix}165\\55\end{bmatrix}=a_1v_1+a_2v_2$

and $a_1=5.4$, $a_2=121.3$

$v_1=\begin{bmatrix}30.48\\0\end{bmatrix}$, $v_2=\begin{bmatrix}0\\0.45\end{bmatrix}$

Let’s represent all of these equations in a single matrix format as follows:

$$\begin{bmatrix}165\\55\end{bmatrix}=\begin{bmatrix}30.48&0\\0&0.45\end{bmatrix}\begin{bmatrix}5.4\\121.3\end{bmatrix}$$

$$\begin{bmatrix}165\\55\end{bmatrix}=M\begin{bmatrix}5.4\\121.3\end{bmatrix}$$

Here, you can see that ‘M’ is the change of basis matrix. Now, if you want to obtain the ft-lbs equivalent of 165 cm and 55 kg, then you need to perform the following operation:
$$\begin{bmatrix}5.4\\121.3\end{bmatrix} = M^{-1}\begin{bmatrix}165\\55\end{bmatrix}$$

To generalise the result given above, you can refer to the following image.  
 

![Change of Basis](https://i.ibb.co/H2d1J5c/Change-of-Basis.png)

In this image, both M and inv(M) are the change of basis matrix according to which basis system you want to convert from which basis system.

Before going to the next discussion let’s understand the inverse of a matrix in brief.

Suppose there is a matrix ‘A’ and its inverse matrix is ‘B’ then AB= I where ‘I’ would be an identity matrix: 

A 2X2 identity matrix will look like.

$$I=\begin{bmatrix}1&0\\0&1\end{bmatrix}$$

Keep in mind that the inverse is only possible for the square matrix i.e. the number of rows is equal to the number of columns.

Now, let’s go through another example of basis change to understand this in detail. 

**VIDEO**

Let’s consider the following example where  a vector (4, 3) is represented as a linear combination of two other vectors, (-1, 3) and (2, -1). 

$$\begin{bmatrix}4\\3\end{bmatrix}=2\begin{bmatrix}-1\\3\end{bmatrix}+3\begin{bmatrix}2\\-1\end{bmatrix}$$

Suppose

$v=\begin{bmatrix}4\\3\end{bmatrix}$,  $v_1=\begin{bmatrix}-1\\3\end{bmatrix}$,  $v_2=\begin{bmatrix}2\\-1\end{bmatrix}$

Considering the definition of the basis vector, it can be concluded that because you are able to represent the ‘v’ vector as a linear combination of v1 and v2, the new basis vectors can be v1 and v2. And the corresponding vector in the new basis vectors will be ‘b’.

$b=\begin{bmatrix}2\\3\end{bmatrix}$

Let’s represent the equation given above in a single matrix format.  
 
$$\begin{bmatrix}4\\3\end{bmatrix}=\begin{bmatrix}-1&2\\3&-1\end{bmatrix}\begin{bmatrix}2\\3\end{bmatrix}$$

An important point that you should note is: 

Suppose you have a point, say (4, 3) in the x-y / i-j basis and you want to represent the same point on v1 (-1, 3) and v2 (2, -1) basis, then you need to represent the (4, 3) point as a linear combination of **v1** and v2. So, the coefficient of the linear combination, i.e., (2, 3), will be the new representation of the same point in the be v1 and v2 basis. 

Hence, you can conclude that the change of basis from one system to another can be done by multiplying the change of the basis matrix as shown in the image below.

![Change of Basis](https://i.ibb.co/6BCg9wP/Change-of-Basis2.png)

With this, you have understood the concept of basis change.

#### Different basis vector

Qn: Let's say that you're representing the vector  $\begin{bmatrix}120\\35\end{bmatrix}$ using a new set of basis vectors  $\begin{bmatrix}1\\c\end{bmatrix}$ and  $\begin{bmatrix}d\\0.25\end{bmatrix}$, where  c and d are unknowns. In this new representation, that vector in the original standard basis is now written as  $\begin{bmatrix}30\\20\end{bmatrix}$ From this information, find out the values of $c$ and $d$.

- c =1,  d = 4.5

- c = 4.5 , d = 1 

- c = 1, d =4

- c = 4 , d =1 

Ans: A. *Write the linear combination of the vectors and solve for c and d by comparing the same elements of the matrices on both the sides.*

#### Change of basis

Qn: Suppose you have data on crude oil tanks. This data contains the volume, density and weight of the tank. 

You have been given the following relations.  
1 litre = 0.001 cubic metre  
1 kg/L = 10,00,000 grams/cubic metre  
1 kg = 1,000 grams

What will be the change of basis matrix if you want to convert the basis from cubic metre, grams/cubic metre and grams to litre, kg/L and kg?

- $\begin{bmatrix}10^{3}&0&0\\0&10^{-6}&0\\0&0&10^{-3}\end{bmatrix}$

- $\begin{bmatrix}10^{3}&0&0\\0&10^{-6}&0\\0&0&10^{-3}\end{bmatrix}^{-1}$

- $\begin{bmatrix}10^{-3}&0&0\\0&10^{6}&0\\0&0&10^{3}\end{bmatrix}$

- $\begin{bmatrix}10^{-3}&0&0\\0&10^{6}&0\\0&0&10^{3}\end{bmatrix}^{-1}$

Ans: A & D. *This option is correct. Suppose there is a tank with the following details: 10 L, 0.01 kg/L, 0.1 kg. When you represent it in the linear combination of a new basis system, then it will be represented in the following way.*
$$\begin{bmatrix}10\\0.01\\0.1\end{bmatrix}=10^{-2}\begin{bmatrix}10^3\\0\\0\end{bmatrix} + 10^4\begin{bmatrix}0\\10^{-6}\\0\end{bmatrix}+10^2\begin{bmatrix}0\\0\\10^{-3}\end{bmatrix}$$
*So, the change of basis matrix will be:*
$$\begin{bmatrix}10^{3}&0&0\\0&10^{-6}&0\\0&0&10^{-3}\end{bmatrix}=\begin{bmatrix}10^{-3}&0&0\\0&10^{6}&0\\0&0&10^{3}\end{bmatrix}^{-1}$$
