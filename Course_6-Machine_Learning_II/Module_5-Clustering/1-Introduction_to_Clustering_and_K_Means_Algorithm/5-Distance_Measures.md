# Distance Measures

In the previous segments, you developed an understanding of how clustering works. It groups objects on the basis of their similarity or closeness to each other.

In simple terms, the algorithm needs to find data points whose values are more alike. These data points can then belong to the same cluster. Clustering algorithms do this by utilising  a ‘distance measure’. Let's watch the next video to learn about this measure in detail.

**VIDEO**

There are three types of distance measures, which are as follows:

- Classical distance measures
- Correlation-based distance measures
- Edit distance measures

These distance measures are not limited to clustering algorithms; they are common to all machine learning algorithms. The common distance measures used in the case of clustering algorithms are the classical distance measures. You will learn these measures in the upcoming video. For an in-depth understanding of other distance measures, you can refer to the optional segment titled '**Other Distance Measures**'

There are three major types of classical distance measures, which are as follows:

- **Euclidean distance measure**  
  The Euclidean distance represents the distance between two points, which can be measured using a ruler. In a two dimensional space, the Euclidean distance between two points $(x_1,\ y_1)$ and $(x_2,\ y_2)$ is given as follows:
  $$\Huge\sqrt{(x_2-x_1)^2+1(y_2-y_1)^2}$$

- For higher dimensions, this distance can be generalised as follows:  
  $d(p_i,\ q_i)=\sqrt{\sum{(p_i−q_i)^2}}$  
  where p and q are observations, and i denotes a feature.  
   

- **Manhattan distance measure**  
  The Manhattan distance represents the distance between two points measured along the axes at the right angles. In a two-dimensional space, the Manhattan distance between two points (x1,y1) and (x2,y2) is given as follows:
  $$\Huge|x_2-x_1|+|y_2-y_1|$$
  For higher dimensions, this distance can be generalised as follows:  
  $d(p_i,\ q_i)=\sum{|p_i−q_i|}$  
   

- **Minkowski distance measure**  
  The Minkowski distance is a generalisation of both the Euclidean and Manhattan distance measures. For n dimensions, the Minkowski distance between two observations, p and q, can be written as follows:
  $$\Huge(\sum|p_i-q_i|^p)^{1/p}$$
  
  The table given below lists the distance measures for different p values.  
  
  |              |                    |
  | ------------ | ------------------ |
  | p = 1        | Manhattan distance |
  | p = 2        | Euclidean distance |
  | p = $\infty$ | Chebyshev distance |
  
  - For $p=1$ and $p=2$, the Minkowski distance transforms into the Manhattan distance and the Euclidean distance, respectively.
  - At $p=\infty$, the distance measure is transformed into the Chebyshev distance. This distance is also known as the maximum value distance
  - For two points, p and q, the Chebyshev distance is given as follows:   $d(p_i,\ qi)=max(|p_i−q_i|)$. You can refer to this [link](https://proofwiki.org/wiki/Chebyshev_Distance_is_Limit_of_P-Product_Metric) for an in-depth understanding of the mathematics behind this.

## Data Standardisation

Unfortunately, applying distance measures between the two points is not enough. Distance measures are highly influenced by outliers and other factors. Therefore, you will perform a preprocessing step known as data standardisation. Let's watch the next video to learn more about this step.

**VIDEO**

Classical distance measures such as the Euclidean distance are highly influenced by outliers. They are also biased towards features that have high values. Consider the following example:

![Observation Outlier](https://i.ibb.co/bQwGXxv/Observation-Outlier.png)

Suppose you fail to identify the outlier and evaluate the distance measured between the observations. In this case, the Euclidean distance will be calculated as follows:

![Biased Towards Income](https://i.ibb.co/w7gF6h8/Biased-Towards-Income.png)

The value comes out to be **d = 400000.001311**

As you can see, the euclidean distance is highly biased towards income, whereas the features of age and distance have a negligible effect on the overall euclidean distance. Now, suppose the distance metric is changed from kilometre (km) to centimetre (cm). In this case, 30 km will become 30,00,000 cm. If you use this metric while calculating the distance, then the distance measure will become biased towards income and distance, and the value will come out to be **d = 3224903.099323**

In order to avoid this bias, it is important to bring each feature to a unitless and common scale. This is done with the help of data standardisation. Standardisation of data refers to converting the features into z-scores with mean 0 and standard deviation 1. The data is transformed using the following formula:
$$\Huge x_{scaled}=\dfrac{x-mean}{sd}$$

In the example given below, you can observe that all the values are brought down to a common scale, and the distance measure is no longer biased to any one feature.

![Scaling and Distance Measure](https://i.ibb.co/vQdr4CR/Scaling-and-Distance-Measure.png)

#### Euclidean Distance

Qn: Consider the two points A(7,50) and B(23,34). Compute the Euclidean distance between these points. [Note: Round off the answer to two decimal places.]

- 21.78

- 25.47

- 23.12

- 22.63

Ans: D. *The Euclidean distance between the two points is given by the following formula:* $\sqrt{(23-7)^2+(34-50)^2}=\sqrt{(16^2+16^2)}=\sqrt{512}=22.627416998\approx22.63$

#### Manhattan Distance

Qn: Consider the same two points given in the previous question, A(7,50) and B(23,34). Compute the Manhattan distance between these points. [Note: Round off the answer to two decimal places.]

- 32

- 30

- 38

- 28

Ans:A. *The Manhattan distance between the two points (X1, X2) and (Y1, Y2) is given by the following: $|x_1-x_2|+|y_1-y_2|$.* 
*By substituting the given values, you get $|23-7|+|34-50|=32$.*

#### Chebyshev Distance

Calculate the Chebyshev distance between the two points given in the table below.

|         | Feature 1 | Feature 2 | Feature 3 | Feature 4 |
| ------- | --------- | --------- | --------- | --------- |
| Point 1 | 2         | 3         | 1         | -1        |
| Point 2 | 4         | -1        | 0         | -2        |

- 2

- 4

- 1

- -2

Ans: A. $d(p,\ q)=max(|2-4|,\ |3-(-1)|,\ |1-0|,\ |(-1)-(-2)|)=max(|-2|,\ |4|,\ |1|,\ |1|)=4$

#### Data Standardisation

Qn: Consider the following two points that have been taken from a data set:

| ID  | Height | Weight |
| --- | ------ | ------ |
| 1   | 150    | 50     |
| 2   | 180    | 60     |

You can find the statistics for the data given below.

|        | Mean | Standard Deviation |
| ------ | ---- | ------------------ |
| Weight | 70   | 10                 |
| Height | 160  | 20                 |

Find the values of the data after standardisation has been completed.

- | ID  | Height | Weight |
  | --- | ------ | ------ |
  | 1   | -0.5   | -2     |
  | 2   | -2     | 1      |

- | ID  | Height | Weight |
  | --- | ------ | ------ |
  | 1   | -0.5   | -2     |
  | 2   | 1      | -1     |

- | ID  | Height | Weight |
  | --- | ------ | ------ |
  | 1   | -2     | -0.5   |
  | 2   | -1     | 1      |

- | ID  | Height | Weight |
  | --- | ------ | ------ |
  | 1   | 0.5    | 2      |
  | 2   | 1      | 1      |

Ans: C.

| ID  | Height              | Weight            |
| --- | ------------------- | ----------------- |
| 1   | $(150-160)/20=-0.5$ | $(50-70)/10=-2$   |
| 2   | $(180-160)/20=1$    | $(60-70)/10=-0.5$ |

Now that you have understood the importance of feature scaling, you need to learn to identify the clustering tendency of the data before you apply any clustering algorithm. Cluster tendency refers to checking whether the given data provides meaningful clusters or not. For this, you will learn an interesting statistic known as the Hopkins statistic in the next segment.

#### Additional Links
[4 Distance Measures for Machine Learning](https://machinelearningmastery.com/distance-measures-for-machine-learning/)
