# Advantages, Disadvantages and Applications

You now have a good understanding of the ensemble class of models and the features of the Random Forest model. In this segment, you will learn about the advantages and disadvantages of the random forest model. 

Apart from the general advantages of ensembles, random forests have significant benefits owing to their origins in decision trees and other linear models. However, it also has some disadvantages. In the next video, you will learn about the advantages and disadvantages of random forests.

**VIDEO**

Some of the advantages mentioned in the video are as follows:

-   **Variety**: Similar to decision trees, the random forest model can be used for both types of models, which are Regression and Classification. 
-   **Stability**: Stability arises because the answers given by a large number of trees average out the instability caused owing to the error. The random forest model has a lower model variance than that of an ordinary individual tree. Also, the model becomes robust with the increase in the number of trees instead of becoming complex.
-   **Immunity to the curse of dimensionality**: Since each tree does not consider all the features, the feature space (the number of features that a model has to consider) reduces. It makes an algorithm immune to the curse of dimensionality. Also, a significant feature space comes with computational and complexity issues.
-   **Parallelisation**: You need multiple trees to make a forest. Since each tree is built independently on different data and attributes, they can be executed parallelly during implementation. It implies that you can make full use of your multi-core CPU to build random forests. Suppose there are four cores and 100 trees to be constructed, each core can build 25 trees to make a forest.

Disadvantages of the random forest model:

-   **Lack of interpretability**: The random forest model uses bagging as the ensemble technique that suffers from a lack of interpretability. Owing to a collection of trees, you cannot make clear decisions as was possible in the case of decision trees. Hence, decision trees will be preferred over this model if model interpretation is the priority.
-   **High computational costs**: As you increase the number of trees, the random forest model gets better. However, it comes with an associated cost in terms of high computational costs. To build and evaluate a random forest model, you will require to process hundreds or thousands of trees to reach the final decision. Hence, the algorithm must be implemented accordingly.

## Industrial Applications

As discussed at the start of the module, random forests find great applications in the following industries:

-   **Medicine**: Random forests have been actively used in the medical industry for detection and study purposes. They have been quite impressive in identifying diseases such as cancer-based on patients' test records. The feature selection scheme of RF has also helped in identifying important genes of biological significance.
-   **Motion sensing**: The example of Microsoft Kinect mentioned at the start of the module reflects how random forest can be effectively used to detect movements of an individual.
-   **Finance**: Owing to its high accuracy and diversity, the random forest model can be effectively used in predicting trends in the stock market.
-   **Banking**: The random forest model can be effectively used to detect fraudulent transactions in the banking sector. The model has the capability to incorporate multiple features that can help in the accurate detection of whether the customer is loyal or a fraud.
-   **Astronomy**: Multiple experiments have revealed that random forests are effective in classifying astronomical objects. Different attributes of the model such as feature selection, feature weighting and detection of outliers have made it a popular choice.

Now that you have come to the end of the session, let's summarise the elements in the next segment.