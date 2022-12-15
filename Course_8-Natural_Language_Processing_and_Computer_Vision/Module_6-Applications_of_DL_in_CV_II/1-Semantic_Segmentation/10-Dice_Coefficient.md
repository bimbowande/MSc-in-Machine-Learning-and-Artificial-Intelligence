# Dice Coefficient

You are already aware that building a machine learning model is always accompanied by different evaluation metrics to validate the performance of the model. The start of the session covered how pixel-wise cross-entropy loss can be used to evaluate the image segmentation models. This segment will cover another metric, the **Dice coefficient**. It is similar to the Intersection over Union (IoU) metric but uses a different formula for estimating the performance of the model.

Let’s hear more about this new metric in the upcoming video.

**VIDEO**

As highlighted in the video, the pixel-wise cross-entropy loss has different challenges associated with it. Since each pixel is examined individually, the function doesn’t seem to perform well in the case of class imbalance due to unequal representation of the classes in the image. All these challenges gave rise to the Dice coefficient.

The dice coefficient is similar to the IoU metric which tries to measure the overlap between the actual mask and the mask predicted by the architecture.  As highlighted in the video, the value of the metric ranges from 0 to 1.

-   1 denotes perfect and complete overlap between the ground truth and the model prediction. (Best case)
-   0 denotes that there is no overlap between the two. (Worst case)

The dice coefficient loss function is defined as _**1-DC**_. Therefore, if the dice coefficient loss is used, the final model will try to minimize the given metric.

#### Dice Coefficient

Compute the dice coefficient for the image below.

![Dice Coefficient](https://i.ibb.co/mGpsxbc/Io-U-Example.png)

- 18%

- 21%

- 24%

- 27%

Ans: B. *The dice coefficient is equal to $\dfrac{2 * \text{Area of intersection}}{\text{Combined Area}}$. The area of intersection is 12 and the combined area is $(12+100)=112$. Hence, the dice coefficient is $21\%$.*

Qn: Compute the dice coefficient loss for the image below.

![Dice Coefficient](https://i.ibb.co/mGpsxbc/Io-U-Example.png)

- 82%

- 79%

- 76%

- 73%

Ans: B. *Dice coefficient loss is equal to $1−DC$.*

Now, you have a theoretical understanding of the concepts associated with semantic segmentation. The next segment will focus on the case study for lung segmentation using the U-Net framework.