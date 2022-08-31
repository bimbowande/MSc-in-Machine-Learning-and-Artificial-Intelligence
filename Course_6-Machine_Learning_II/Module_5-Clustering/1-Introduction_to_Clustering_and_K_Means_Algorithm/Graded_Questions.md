# Graded Questions

#### Clustering

Qn: Which of the following are the applications of clustering?

- Looking at social media behaviour to determine the types of online communities that exist

- Identifying consumer segments and their properties to position products appropriately

- Identifying patterns of crime in the different regions of a city and managing police enforcement based on the frequency and type of crime committed

- All of the above

Ans: D. *All the options given above are activities that involve looking at data and identifying hidden patterns and properties and also determining which data is different from others and in what ways.*

#### Unsupervised Learning

Qn: Which of the following is an instance of unsupervised learning?

- Learning to predict the number of hours it takes to reach a destination, given the day of the week, time, source and destination as input

- Learning to decide if a credit card transaction is fraudulent or not based on pre-labelled data

- Learning to predict the price of a used car

- Learning behaviours of various users by analysing their interaction on a website

Ans: D. *Learning the behaviour of users involves grouping the users with similar behaviours and interpreting the characteristics of the various groups formed. The nature of behaviours is not predetermined. Thus, this is a case of clustering.*

#### Types of Segmentation

Qn: Suppose you are an analyst at a global laptop manufacturing company and are given the task of deciding whether the company should enter the Indian market or not. You try to estimate the market size by first dividing the market on the basis of types of people who use a laptop, such as students and working professionals, and their expenditure capacity to get an estimate of the total market size and the characteristics of each segment. Which type of segmentation is this?

- Behavioural segmentation

- Attitudinal segmentation

- Demographic segmentation

- None of the above

Ans: C. *You are performing a demographic segmentation since you are looking at the income and the profession of the people using laptops. Observe how this is much simpler than finding data about actual laptop purchasing history of customers and then trying to estimate the market size based on that data.*

#### Euclidean Distance

Qn: Consider the two points A(7, 50) and B(23, 34). Which point is closer (or more similar) to point C(12, 12)?

- B

- A

- Both are equidistant from point C

- None of the above

Ans: A. *The Euclidean distance between two points $(X_1,\ Y_1)$ and $(X_2,\ Y_2)$ is given by the following formula: $\sqrt{(X_1−X_2)^2+(Y_1−Y_2)^2}$. Substituting the values for A, C and B, C in the given expression, you get the distance AC as $\sqrt{1469}=38.33$ and BC as $\sqrt{605}=24.59$. Therefore, point B is closer to C.*

#### Hopkins Statistic

Qn: Suppose a data set has the scatter plot given below.

![Hopkins Statistics Qn](https://i.ibb.co/fd7g8Nb/Hopkins-Statistics-Qn.jpg)

Which of the following statements will be true? (H = Hopkins statistic)

- H≈1

- H > 0.5

- H < 0.5

Ans: C.

#### K-means Algorithm

Qn: Consider three cluster centres, A(2,3), B(4,5) and C(6,2). A point (1,2) is to be assigned to one of these clusters. According to the K-means clustering concepts and using the Euclidean distance as the measure of closeness, which cluster should it be assigned to?

- A

- B

- C

- Any of the above(It does not matter since it has to be randomly selected the first time.)

Ans: A. *According to the K-means algorithm, the point should be assigned to the centre with the minimum distance from the point. The distances for A, B, C are √2, √18 and  √25 , respectively; hence, it will be assigned to cluster A.*

#### K-means Algorithm

Qn: Which of the following options are the prerequisites for the K-means algorithm?

A) The initial centres should be very close to each other

B) Selection of number of clusters

C) Selection of initial centroids

- Only A

- B and C

- A and B

- A, B and C

Ans: B. *Note that the K-means algorithm requires the initial centres to be far apart.*

#### K-means Algorithm

Qn: Consider the points and the cluster membership depicted in the image given below.

![K-Means Algorithm Qn](https://i.ibb.co/C76qKnB/K-Means-Algorithm-Qn.jpg)

Does this arrangement of points indicate a convergence if k-means is used to cluster these points in two clusters?

- Yes

- No

Ans: B. *The centre of the left cluster is closer to the leftmost point of the right cluster than the centre of the right cluster. Hence, if there is one more iteration, then this membership of points to clusters will change. This means that these points do not represent a convergence.*

#### K-means Algorithm

Qn: Suppose the K-means algorithm is run on a data set. You are provided with two possible clusterings. Which of these clusterings is more likely than the other?

Note: The points represented below are equally spaced out in the Euclidean space. 

![K-Means Clustering Result 1](https://i.ibb.co/jDCyXCm/K-Means-Clustering-Result-1.jpg)

![K-Means Clustering Result 2](https://i.ibb.co/qY3KKQX/K-Means-Clustering-Result-2.jpg)

- Clustering result 1

- Clustering result 2

- Both are likely.

- Both are unlikely.

Ans: C. *Depending on different initialisations, you may get either of these clusterings.*

#### K-means Algorithm

Qn: Which of the following can act as the possible termination condition in the K-means algorithm? (Note: More than one option may be correct.)

- Keeping a fixed number of iterations

- Assignment of observations to clusters does not change for successive iterations.

- Centroids do not change between successive iterations.

- The change in the value of the cost function is below a threshold value.

Ans: All of the above.

- *We can choose to fix the number of iterations if we are confident that the algorithm will converge within the given number of iterations.*

- *If the assignment of observations to clusters does not change, it means that the algorithm has reached certain minima.*

- *If the points are no longer assigned between successive iterations, the computed centroids will also stay the same.*

- *When the algorithm reaches some minima, it indicates that the algorithm has converged. On running further iterations, cluster centroids do not change, and the cost function value remains constant. Hence, if the value of cost function does not change, it can be used to justify the termination of the algorithm.*
