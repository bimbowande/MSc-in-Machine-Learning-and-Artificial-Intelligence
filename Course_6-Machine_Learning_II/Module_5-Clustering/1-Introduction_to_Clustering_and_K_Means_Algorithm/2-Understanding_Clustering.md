# Understanding Clustering

In the previous modules, you learnt about various supervised machine learning algorithms. These algorithms use labelled data to make predictions. For example, an email is classified as ‘spam’ or ‘non-spam’, or a bank customer being predicted as ‘good’ or ‘bad’ involves a target variable, Y, which needs to be predicted.

On the other hand, in unsupervised learning, you need not make predictions because you do not have a target or an outcome variable. Here, the objective is to discover interesting patterns in the data; for example, whether there are any subgroups or ‘clusters’ among a bank’s customers.

Let’s watch the next video to learn more about clustering.

**VIDEO**

Clustering involves grouping objects in such a way that objects belonging to the same cluster or group are similar. This similarity is a measure of how alike two data points are. This similarity measure is quantified by the distance measured between two points. You will learn more about distance measures in the subsequent segments. In data science, similarity indicates the strength of the relationship between two distinct objects. Consider the scatter plot provided below. Using a clustering algorithm, we have grouped the data points into three clusters and depicted them in red, blue and green.

![Clustering Basic](https://i.ibb.co/0Vgv9fP/Clustering-Basic.png)

## Classification vs Clustering

Clustering and classification are both fundamental approaches in data mining, and students often tend to get confused between the two. The table given below lists the differences between classification and clustering.

![Classification vs Clustering](https://i.ibb.co/XXfcvRv/Classification-vs-Clustering.png)

## Applications of Clustering

In the next video, you will learn about some practical applications of clustering in different industries such as e-commerce and banking.

**VIDEO**

In the video above, you learn about the different applications of clustering, which are as follows:

-   **E-Commerce industry**: In this industry, clustering is used to identify different segments of customers within the customer base. The characteristics/profiles of these customer clusters are used to devise target-specific (or cluster-specific) marketing campaigns. This process is known as Customer Segmentation. You will learn about this process in the next segment.  
      
    ![E-Commerce Industry](https://i.ibb.co/fNFv2Dd/E-Commerce-Industry.png)

-   **Banking industry**: The data of fraudulent customers tend to act as outliers in the dataset. These outliers can be easily detected through clustering algorithms, as they form a cluster of their own or not be assigned to any cluster due to their uniqueness. This can help in various use cases such as loyalty tiering and fraud.
    
    ![Banking Industry](https://i.ibb.co/9p0TJth/Banking-Industry.png)
    
-   **Market research**: Before launching a certain product into the market, thorough market research is performed in order to understand customer needs and improve on product features accordingly. Clustering is performed as a part of market research to identify specific groups within a population that would be more likely to purchase the product.
    
	 ![Market Research](https://i.ibb.co/7XgRnrS/Market-Research.png)
    
      
     
-   **Telecom industry**: In this industry, clustering is used to identify network congestion within specific markets. This helps in estimating the capacity for network expansion.  
     
-   Other Applications
    -   **Document clustering**: Clustering is performed in order to cluster similar types of documents or text. One such use case is topic clustering, wherein you group pieces of information or text that share a similar topic, such as sports or politics.
    -   **Image clustering**: Image clustering is the process of clustering similar-looking images. Consider the example of running a clustering algorithm on a dataset consisting of pictures of dogs and cats. Since the pictures of cats are more similar to one another than those of dogs, they would be grouped into one cluster. Similarly, all the pictures of dogs would be grouped in another cluster.

In the next segment, you will be introduced to a real-life application of clustering involving grouping customers of an online store into different clusters and making a separate targeted marketing strategy for each group.

#### Unsupervised Learning

Qn: You learnt about three different types of machine learning techniques: regression, classification and clustering. Which of the following techniques does not require bifurcation of data points into dependent and independent variables?

- Regression

- Classification

- Clustering

- All of the above

Ans: C. *In clustering, data points are grouped into different clusters or groups based on the given set of attributes. There are no dependent or independent variables involved here.*

#### Classification vs Clustering

Qn: Clustering is an unsupervised machine learning technique. It is used to place data elements into related groups without any prior knowledge of the group definitions. Which of the following is considered a clustering task?

- A baby is given some toys to play with. These toys consist of various animals, vehicles and houses, but the baby is unaware of these categories. The baby chooses different toys and starts making different groups of the toys based on what it thinks are similar.

- A data set containing various features of an AC, such as length, width, height and split/window, is provided. A new design of an AC is introduced in the market. The algorithm needs to predict whether the new AC is split/window, given its dimensions.

Ans: A. *Since the baby is grouping objects based on their features and has no idea of any pre-existing categories, this can be considered a clustering task.*

## Additional Reading

To read more about business cases in which clustering is used, you can click [here](https://datafloq.com/read/7-innovative-uses-of-clustering-algorithms/6224).