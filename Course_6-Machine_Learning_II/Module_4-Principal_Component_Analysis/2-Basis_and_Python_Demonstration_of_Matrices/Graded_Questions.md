# Graded Questions

In this segment, you will summarise the concept of change in basis. Let’s understand this through an example. Imagine that you are visiting another planet for exploratory purposes that will help you determine whether this planet has intelligent life or not. Assume that you meet an alien there and you tell it where you came from and share the location of Earth from that planet.

You realise that the standard basis on that planet is not the same as that of Earth. You use basis B1 = {i, j} where i and j are the orthogonal vectors in the x-y plane, while the alien uses basis B2 = {i-2j, i+j}.

You want to show the alien how far the Earth is from that planet. You know the position in your basis, i.e., (21, 12) in B1. To communicate this location to the aliens, you will have to tell them this same location or vector in their Basis B2.

You can use the following lines of code to calculate the required results in Python.

In order to create a 2 X 2 matrix ‘M’ in Python, you can use the following lines of code.

$M=\begin{bmatrix}a&c\\b&d\end{bmatrix}$

```python
M = np.array([[a, b], [c, d]]).T
```

To find the inverse of the matrix ‘M’, you can write the following lines of code.  
 

```python
M = np.linalg.inv(M)
```

Now, suppose you want to multiply a matrix ‘M’ with a vector ‘$v$’.  

$v=\begin{bmatrix}p\\q\end{bmatrix}$

```python
M @ np.array([p,q])
```

Now, let’s answer the following questions.

Question 1/3

Mandatory

#### Change of basis matrix

What will be the change of basis matrix if you convert any location point which is in your basis system, i.e., B1 to an alien basis system, i.e., B2?

- $\begin{bmatrix}1&1\\-2&1\end{bmatrix}$

- $\begin{bmatrix}1&1\\-2&1\end{bmatrix}^{-1}$

- $\begin{bmatrix}1&1\\1&-2\end{bmatrix}$

- $\begin{bmatrix}1&1\\1&-2\end{bmatrix}^{-1}$

Ans: B. Suppose there is point ‘v’ (a, b) in B2 basis and if you change the basis of ‘v’ into B1 and get (1, 2) in B1, then the linear equation for the basis change will be:*
$$\begin{bmatrix}1\\2\end{bmatrix}=a\begin{bmatrix}1\\-2\end{bmatrix}+b\begin{bmatrix}1\\1\end{bmatrix}$$
*Now, to get the (a, b), you have to manipulate this equation. And if you do so, you will get the following equation.*
$$\begin{bmatrix}1&1\\-2&1\end{bmatrix}^{-1}*\begin{bmatrix}1\\2\end{bmatrix}=\begin{bmatrix}a\\b\end{bmatrix}$$
#### Position of Saturn

Qn: You want to tell the alien about the planet Saturn. To share the location of Saturn with it, you will need to convert the vector to the alien's basis. The location of Saturn in your basis is (25, 28).

- $\begin{bmatrix}27\\1\end{bmatrix}$

- $\begin{bmatrix}-31\\53\end{bmatrix}$

- $\begin{bmatrix}53\\-22\end{bmatrix}$

- $\begin{bmatrix}-1\\26\end{bmatrix}$

Ans: D. *You can multiply by the matrix.*
$$\begin{bmatrix}1&1\\-2&1\end{bmatrix}^{-1}*\begin{bmatrix}25\\28\end{bmatrix}=\begin{bmatrix}-1\\26\end{bmatrix}$$

#### Position of Kappa

Qn: The alien shares with you the location of a planet called Kappa, which has intelligent life on it. However, the position is on the alien's basis B2. This information will be useful to the people on Earth; so, you have to convert the position to the Earth's basis B1. So, the representation of Kappa in the alien's basis is $\begin{bmatrix}-3\\12\end{bmatrix}$. What is the representation in your basis?

- $\begin{bmatrix}7\\5\end{bmatrix}$

- $\begin{bmatrix}9\\18\end{bmatrix}$

- $\begin{bmatrix}-27\\9\end{bmatrix}$

- $\begin{bmatrix}-5\\2\end{bmatrix}$

Ans: B. *The representation can be multiplied by the matrix, which is obtained by writing the basis of the alien as column vectors.*
$$\begin{bmatrix}1&1\\-2&1\end{bmatrix}*\begin{bmatrix}-3\\12\end{bmatrix}=\begin{bmatrix}9\\18\end{bmatrix}$$
