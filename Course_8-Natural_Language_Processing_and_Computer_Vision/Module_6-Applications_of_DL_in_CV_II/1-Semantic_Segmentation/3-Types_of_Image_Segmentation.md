# Types of Image Segmentation

In this segment, you will learn about the different types of image segmentation. Image segmentation helps to segment the image into different sections based on the class to which it belongs. With this feature, you have two options. You can either analyse all the objects in the image and map the area of all the objects like cars, humans, trees, etc., or you can restrict the analysis to a particular class (like humans) by identifying the different instances present in the image.

Let’s try to understand both the variations of image segmentation in the upcoming video.

**VIDEO**

As mentioned in the video, there are two types of image segmentation:

1.  Semantic segmentation
2.  Instance segmentation

![Types of Image Segmentation](https://i.ibb.co/hMp2ZwX/Types-of-Image-Segmentation.png)

Source: PASCAL VOC, [Harshall Lamba - Towards Data Science](https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47)

Semantic segmentation is used to segment the different classes present in an image. Each pixel is associated with a different object or a class. In the above image, you can see that all the individuals are segmented as ‘person’. However, in the case of instance segmentation, this is further extended by segmenting each instance of a class separately. As you can see in the image above, each person is highlighted using different colors.

Based on the use case, you can choose from either of these segmentation applications. Let’s try to understand this using an example from sports analytics. Consider that you want to analyse the movement of players in a football match. If you are only interested in the formations or the movement of the teams in the match,  you can segment all the players under one category. However, if you want to dig deeper into the performance of each player, you will have to segment them individually to separate them from one another. Therefore, you can choose either of these applications based on the use case. 

#### Types of Image Segmentation

Qn: Which of the following statements is correct?

- Semantic segmentation can be used to analyse each instance of a class individually.

- Instance segmentation focuses on only one class (like humans or cars) in an image.

- None of the above.

Ans:C. 

-   Semantic segmentation segments all the instances of a class as a single class. Therefore, individual instances cannot be analysed using this application.

-   Instance segmentation can highlight different instances of multiple classes in a single image. It is not restricted to a single class.

Let us now understand the inputs associated with the task of segmentation. You have seen that in the case of object detection, the model expects the image and the associated bounding boxes and labels as input. 

![Image Segmentation Input](https://i.ibb.co/mBtZtxw/Image-Segmentation-Input.png)

Similarly, the task of image segmentation requires the user to provide additional details along with each image. Let’s hear from Georgios about this in the upcoming video.

**VIDEO**

The above video highlights that building an image segmentation model requires images along with the annotated masks (masks with labels). These masks help the model to learn the shape, structure or other features associated with each class to distinguish them from one another.

![Binary Mask](https://i.ibb.co/DprrmY4/Binary-Mask.png)

Example of a binary mask

The next segment will now help you with the different applications of image segmentation.