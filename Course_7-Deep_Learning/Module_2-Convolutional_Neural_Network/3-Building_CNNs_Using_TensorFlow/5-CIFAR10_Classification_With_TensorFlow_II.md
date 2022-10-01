# CIFAR-10 Classification With TensorFlow - II

This segment will help in better intuitive understanding of the visual data. You will be working with the Matplotlib library to explore the different images present in the CIFAR-10 data set.

Let’s hear from Ajay about it in more detail in the upcoming video.

**VIDEO**

This video helped in exploring the different parts of the image independently. The Matplotlib library was used to display the images from the data set on a defined grid. The first 25 data points have been provided along with their labels in the image given below.

![CIFAR10 First 25 Images](https://i.ibb.co/5B85hxR/CIFAR10-First25-Images.jpg)

The information associated with each image is stored in the form of an array, where the first two values denote the height and the width of the image, and the third value represents the three channels (red, green and blue). The heatmaps from the Seaborn library helped in visualising these channels independently.

![Heatmaps different Channels](https://i.ibb.co/mJDc1FC/Heatmaps-different-Channels.jpg)

Later, the video explored one of the channels along with their intensity values. As you can see from the image given below, the red part of the image has the intensity value of 1 in the red channel. The boundary pixels between the object and background have the values 0.6 to 0.9, and the black object in the middle has the pixel values in the range of 0.1 to 0.3, as red is nearly absent in this region.

![Normlaized HeatMap](https://i.ibb.co/mFysCQJ/Normlaized-Heat-Map.jpg)

Additionally, an enhancement factor can be introduced on top of the red cmap to slightly change the intensity of colours throughout the image. This will depict how sensitive the image is to change in the intensity of a channel. A value of one corresponds to no change at all, a value lower than one corresponds to a lower intensity of red, and finally, a value higher than one corresponds to a higher intensity of red.

![HeatMap Color Multiplier](https://i.ibb.co/ByHKsff/Heat-Map-Color-Multiplier.jpg)

Lastly, you learnt how to change the pixel intensity of different channels in an image. An enhancement factor can be helpful when the image quality is low or the boundary is not clearly defined.

Now that you have an idea of the actual data, the next segment will cover how to build a classification model on top of it.