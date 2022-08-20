# Vectors and Matrices Python Demonstration

In this segment you will learn how to handle vectors and matrices using the NumPY library. You will also perform some basic operations on vectors and matrices.

In the next video, let’s hear from Jaidev as he discusses the Python lab session.

You can refer to the following python notebook to have a better understanding while seeing the videos.

Download [Vectors and Matrices](01_linalg_intro.ipynb)

**VIDEO**

In this video, you learnt how to plot vectors on a graph. The codes discussed in the video are summarised below.

-   You imported the two important libraries that you are already aware of. They are:

```python
numpy
matplotlib.pyplot
```

-   In the next code, you wrote a function called ‘draw_vectors’ to plot vectors on a graph. This function is as follows:

```python
COLORS = plt.rcParams['axes.prop_cycle'].by_key()['color'] * 2
def draw_vectors(*vectors, **kwargs):
    X = np.vstack(vectors)
    fig, ax = plt.subplots()
    for i, v in enumerate(X):
        ax.arrow(0, 0, *v, color=COLORS[i], length_includes_head=True,
                 width=0.03, head_width=0.1)
    xmax, ymax = np.abs(X.max(0))
    ax.axis([-xmax - 1, xmax + 1, -ymax -1, ymax + 1])
    ax.set_aspect('equal')
```

-   _**np.vstack(vectors):**_ This particular function is used to stack the sequence of input arrays vertically in order to make a single array. So, if you have two arrays such as [1, 2] and [3, 4], then this function will stack them in the following format. you can refer to [this](https://numpy.org/doc/stable/reference/generated/numpy.vstack.html) link to understand more about this method.

```python
[[1, 2]    
[3, 4]]
```

-   _**fig, ax = plt.subplots()**_: This method provides a way to plot multiple plots on a single figure. Given the number of ‘rows’ and ‘columns’, it returns a tuple (fig, ax), giving a single figure ‘fig’ with an array of axes ‘ax’. 

If you want to plot four plots in a single subplot, then write **fig, _ax = plt.subplots(2, 2)_**. In this code, you get four plots in a single figure and the array ‘ax’ will contain four indexes as ax[0, 0], ax[1, 0], ax[0, 1] and ax[1, 1].

-   _**ax.arrow():**_ This method is used to draw an arrow. Here, you have started a ‘for’ loop, which is getting the vectors as inputs from the stack ‘X’ one by one. These are already defined in the code above and are drawing the vectors on graphs. you can refer to [this](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.arrow.html) link to understand more about this function.
-   _**ax.set_aspect(‘equal’):**_ This function is used in the matplotlib library to set the aspect of the axis scaling, i.e., the ratio of y-unit to x-unit. As you have used ‘equal’ here, it will set the scaling ratio of y-unit to x-unit as equal.

**Note**: In theory, you have understood the vectors in the form of a column matrix. However, in NumPY, the vectors are represented in the form of a row matrix.

In the next lines of code, you saw that the two arrays (vectors) ‘x’ and ‘y’ have been defined. An important point to note here is that when you represent the vector in literature, you denote it with a column matrix but in Python, the vector is defined in the form of an array, which is a row matrix.  
When you apply the **_‘draw_vector(x, y)’_** function to ‘x’ and ‘y’, you get the following graph.

![draw vector](https://i.ibb.co/jMwPGTz/draw-vector.png)

In the next video, you will learn how to define multiple vectors in the form of a single matrix.

**VIDEO**

In the theoretical study of matrix, you learnt that a matrix can be interpreted as a collection of vectors. In the video above, Jaidev defined a matrix ‘X’ as follows:

```python
X = np.array([
    [np.cos(0),          np.sin(0)         ],
    [np.cos(pi / 4),     np.sin(pi / 4)    ],
    [np.cos(pi / 2),     np.sin(pi / 2)    ],
    [np.cos(3 * pi / 4), np.sin(3 * pi / 4)],
    [np.cos(pi),         np.sin(pi)        ],
    [np.cos(5 * pi / 4), np.sin(5 * pi / 4)],
    [np.cos(3 * pi / 2), np.sin(3 * pi / 2)],
    [np.cos(7 * pi / 4), np.sin(7 * pi / 4)]
])
```

In this matrix, a total of eight vectors have been defined. Now, let’s understand the meaning of the term ‘pi’ in this matrix. ‘pi’ is the radian measurement of an angle in degrees and 180 degrees is equivalent to 1 pi. 

_1 pi radian = 180 degrees of angle_

In the code given above, a total of eight vectors are defined, which are 45 degrees (pi/4 radian) apart from each other. Now, when you apply the ‘draw_vectors(*X)’ method on matrix ‘X’, you get the following vector plot.

![](https://images.upgrad.com/17fa1cbd-fa81-4de8-96e6-94b72e9af6ff-img2.png)

In the exercise section, you saw that Jaidev plotted two orthogonal vectors. The orthogonal vectors are vectors that are 90 degrees (pi/2) apart from each other. In the plot given above, the orthogonal vectors to the red vector are in green and orange.

The red and green vectors can be defined as follows:

```python
x = np.array([1, 1])
y = np.array([-1, 1])
```

Then, you can join both x and y into a single matrix ‘X’ to draw them.

```python
X = np.array([1, 1], [-1, 1])
draw_vectors(*X)
```

With this, you have understood the Python codes to draw any vectors on a graph. In the next segment, you will learn about the covariance matrix.

#### Vectors

Qn: Suppose there are three vectors. What will be the angle between these vectors if they are equally spaced in the x-y plane? More than one option can be correct.

- 90 degrees

- pi/2 radian

- 120 degrees

- 2 * pi/3 radian

Ans: C & D. *When three vectors are equally spaced in the x-y plane, then the angle between them will be 360/3, which is 120 degrees (or 2 * pi/3 radian). You can generalise this result for n-vectors. The angle between n-vectors will be 360/n degrees (or 2 * pi/n) if the vectors are equally spaced in the x-y plane.*

Qn: Write the lines of code to plot the four vectors that are equally spaced in the x-y plane.
Ans: 

```python
# code to draw vectors.
COLORS = plt.rcParams['axes.prop_cycle'].by_key()['color'] * 2

def draw_vectors(*vectors, **kwargs):
    X = np.vstack(vectors)
    fig, ax = plt.subplots()
    for i, v in enumerate(X):
        ax.arrow(0, 0, *v, color=COLORS[i], length_includes_head=True,
                 width=0.03, head_width=0.1)
    xmax, ymax = np.abs(X.max(0))
    ax.axis([-xmax - 1, xmax + 1, -ymax -1, ymax + 1])
    ax.set_aspect('equal')

# code to plot the four equally spaced vectors
pi = np.pi

X = np.array([
    [np.cos(0),          np.sin(0)         ],
    [np.cos(pi / 2),     np.sin(pi / 2)    ],
    [np.cos(pi),     np.sin(pi)    ],
    [np.cos(-pi / 2),     np.sin(-pi / 2)    ]
])
draw_vectors(*X)
plt.gca().set_aspect('equal')
```
