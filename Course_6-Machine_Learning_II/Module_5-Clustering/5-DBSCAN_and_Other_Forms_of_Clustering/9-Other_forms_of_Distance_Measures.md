# Other forms of Distance Measures

Besides classical distance measures, you can use correlation and edit-distance measures as well. 

## Correlation Distance Measures

In the next video, you will learn about three important correlation distance measures, which are as follows:

-   Cosine distance measures
    
-   Pearson correlation coefficient
    
-   Spearman correlation coefficient
    

**Note**: Certain parts of the video, you might have already covered as part of the additional content working on the Credit Card Application Approval Model assignment. 

**VIDEO**

Correlation-based distance measures look for overall similarity between objects when their features are highly correlated. It is possible that on a Euclidean scale, they may be quite apart. If you want to identify clusters with similar profiles regardless of their magnitude, then you should opt for correlation-based distance measures.

-   **Cosine distance**: It is the similarity between two vectors of any dimension, which is measured by calculating the angle between them. Given two vectors of attributes A and B, the cosine similarity, θ, is represented using a dot product and magnitude as shown below.
    
    ![](https://lh5.googleusercontent.com/Q2-7sfJNJKCxiqG4uo4932MYxeRgVdh4JJK5m6MZKfxbpYPTpduixCZaBHWlqjcaWhm1qgg2yYxJDa9OL4NbCNU7BW6zj2wFw3fW9vQ6QLtVKxrPd1Gw8Dz6UgTi6mPdZG2hvZ3p)  
    Cosine Distance(a, b) = 1 - Cosine Similarity(a, b)  
    Cosine distance is a common distance measure used in Natural Language Processing (NLP). You can learn more about the use of cosine distance by visiting this [link](https://stackoverflow.com/questions/1746501/can-someone-give-an-example-of-cosine-similarity-in-a-very-simple-graphical-wa).
    

-   **Pearson correlation distance**: In the Linear Regression module, you learnt that the coefficient of determination is represented by R2. This coefficient of determination is nothing but the square of the Pearson correlation coefficient and is represented by r. Pearson correlation coefficient evaluates the linear relationship between two variables. This linear relationship implies that for a given change in one variable, what would be the proportional change in the other variable.  
     
    
-   **Spearman correlation coefficient**: It evaluates the monotonic relationship between two variables. You can learn more about this correlation by visiting this [link](https://www.wikiwand.com/en/Spearman%27s_rank_correlation_coefficient).
    

## Edit Distance Measures

In the next video, you will learn about the two most important types of edit distance measures, which are as follows:

-   Hamming distance
    
-   Levenshtein distance
    

**VIDEO**

The edit distance measure is a way of quantifying the similarity between two strings by counting operations (addition, deletion and substitution), which are required to convert one string into another.

The two important types of edit distance measures are as follows:

-   **Hamming distance**: It allows only one substitution operation, and hence, it can only be used for strings with the same length.
    
-   **Levenshtein distance**: It allows all three operations (addition, deletion and substitution).