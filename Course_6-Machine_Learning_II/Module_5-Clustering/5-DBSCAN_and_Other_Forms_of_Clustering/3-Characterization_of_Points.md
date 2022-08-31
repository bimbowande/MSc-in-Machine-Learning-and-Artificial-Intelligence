# Characterization of Points

In this segment, you will learn about the following three categories into which each point is classified by the DBSCAN clustering algorithm:

-   Core points
    
-   Border points
    
-   Noise points
    

In the upcoming video, you will learn about these points in detail.

**VIDEO**

In the video above, you learnt about the three different types of points in the DBSCAN algorithm: core points, border points and noise points.

Now, let’s take a look at each of these categories in detail.

-   **Core points**: All the points that have at least the Minpts within their EPS distances are known as core points.  
    In the image given below (Minpts = 4), point A is characterised as a core point because it has six points within its EPS distance, which is greater than the value of Minpts, which is 4.
    
    ![](https://images.upgrad.com/b3bde2ba-2945-4784-b5c0-7cb3c2e662a7-pasted%20image%200.png)  
     
    
-   **Border points:** All the points that have at least one core point within their EPS radius are known as border points.  
      
    In the image given below (Minpts = 4), point B is characterised as a border point because it is not a core point but still has at least one core point (point A) within its EPS distance.
    
    ![](https://images.upgrad.com/dd796c32-1388-40a5-b985-3d64ea5aa704-pasted%20image%200%20(1).png)
    
-   **Noise points**: All the points that are neither core points nor border points are called noise points.  
      
    In the image given below (Minpts = 4), point C is characterised as a noise point because it is neither a core point nor a border point.
    
    ![](https://images.upgrad.com/0be6d4b9-364f-4590-b784-8f01ca9d6062-pasted%20image%200%20(2).png)
    

So, now that you have learnt about the parameters required by the DBSCAN algorithm and understood how they are characterised, in the next segment, you will learn about the end-to-end algorithm in detail.

#### Characterisation of Points

Qn: Which of the following points can point A be classified as?

![Characterisation of Points Qn](https://i.ibb.co/W2kM52Z/Characterisation-of-Points-Qn.png)

- Core point

- Border point

- Noise point

Ans: B. *Point A cannot be classified as a core point because the number of points within its EPS distance is less than the Minpts. Within point A’s neighbourhood, point B is a core point because the number of the points in point’s B neighbourhood is 5, which is greater than the EPS. Hence, point A is a border point.*

Qn: Which of the following parameters do you have to select beforehand while using the DBSCAN algorithm? (Note: More than one option may be correct.)

- Core point, border point and noise point

- Epsilon

- Core point and border point

- min_samples

Ans: B & D. *Epsilon and min_samples are required inputs for the DBSCAN algorithm.*
