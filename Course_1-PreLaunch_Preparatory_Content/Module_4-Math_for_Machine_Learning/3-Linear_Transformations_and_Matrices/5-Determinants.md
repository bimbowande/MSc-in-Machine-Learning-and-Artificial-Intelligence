# Determinants

The determinant of a matrix A, usually denoted as |A|, is a numerical value associated with a matrix. You might remember computing determinants of matrices manually from high school math (and perhaps also that whether the determinant is zero or not was an important question in those exercises).

Let's now understand determinants in the light of linear transformations.

## **Visual Intuition: Determinants**

In the last section, you understood that a matrix represents a linear transformation. You also saw that this linear transformation distorts the n-dimensional space. What does a determinant mean from the perspective of space-distortion?

[Watch this video on determinants, courtesy 3Blue1Brown](https://www.youtube.com/watch?v=Ip3X9LOh2dk) to understand what the determinant represents geometrically.

Even though you'll rarely need to compute determinants manually, let's quickly revise how it is done for 2d matrices. Let's say we have the following 2x2 matrix A: $A=\begin{bmatrix}a&b\\c&d\end{bmatrix}$. 
The determinant is given by the **formula**: $det(A)=a*d-b*c$ 

Thus, in the distorted space, 1 square unit of area is multiplied by a factor of $(a∗d−b∗c)$ when matrix A is applied as a linear transformation.
How does this extend to 3x3 matrices?
$$\large{B=\begin{bmatrix}a&b&c\\d&e&f\\g&h&i\end{bmatrix}}$$

The determinant is given by: 
$$\large{det(B)=a*det\left(\begin{bmatrix}e&f\\h&i\end{bmatrix}\right)-b*det\left(\begin{bmatrix}d&f\\g&i\end{bmatrix}\right)+c*det\left(\begin{bmatrix}d&e\\g&h\end{bmatrix}\right)}$$

In 3d space, the determinant represents the magnitude by which the volume, instead of area, is scaled. The process of calculating determinants of matrices of higher dimensions can be scaled up analogously, though you'll usually use Numpy for that. In Numpy, you can compute the determinant using np.linalg.det() as shown below.

```python
# determinant
A = np.array([[2, 3], [-1, 4] ])
np.linalg.det(A)
```

#### Determinants - Intuition

Qn: The determinant of a 2 x 2 matrix being zero means that the matrix:  

- Represents a transformation that squishes the 2d space into a straight line 

- Represents a transformation that squishes the 2d space into a straight line or a single point

- Represents a transformation that expands the 2d space into 3d

Ans: B.

Qn: What is the determinant of the matrix $A=\begin{bmatrix}4&1\\-1&2\end{bmatrix}$?

- 7

- 9

- 8

- 10
Ans: B. *The determinant is given by $(4)*(2) − (−1)*(1) = 9$.*

Qn: Following is a matrix A: 
$$\large{A=\begin{bmatrix}x-4&2\\8&x+2\end{bmatrix}}$$
We know that the determinant of this matrix is 0. What are the possible values of 'x'?
Hint: Apply the formula, get a quadratic equation of the form ax2+bx+c=0 and solve it. This type of determinant computation will appear in the next session on eigenvalues and eigenvectors.

- (3, -5)

- (11, -9)

- (6, -4)

- (7, -5)

Ans: C. *The equation $x^2−2x−24=0$ reduces to $(x−6)*(x+4)=0$.*

In the next segment, you will study an important practical application of matrices - solving **a system of linear equations.**
