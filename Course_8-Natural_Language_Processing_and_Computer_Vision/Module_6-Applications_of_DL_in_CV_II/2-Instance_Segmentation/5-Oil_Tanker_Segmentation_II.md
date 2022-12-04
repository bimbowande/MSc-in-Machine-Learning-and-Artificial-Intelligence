# Oil Tanker Segmentation - II

This segment will mark the beginning of data preparation for the Mask R-CNN architecture. 

The first step will help you read the annotation file provided along with the data set and transform it to generate the masks for each image. Let’s learn about it in the video below.

**VIDEO**

The annotation file provided along with the data set stores the coordinates for the top-left corner and the bottom-right corner of the image. 

![Oil Tanker Segmentation 1](https://i.ibb.co/MNNTN6F/Oil-Tanker-Segmentation-1.jpg)

However, the annotation file is transformed into the following format for further processing:

| image_id | x | y | width | height | class_id |
|----------|---|---|-------|--------|----------|

where,

- _**image_id**_ is the image name and the unique identifier of the image,
- _**x**_ and _**y**_ are the coordinates for the top-left corner of the bounding box,
- _**width**_ and _**height**_ capture the dimensions of the bounding box,
- _**class_id**_ stores the class associated with the bounding box

As the segmentation masks are not provided along with the data set, the bounding boxes will also be used to generate the masks for the images as shown in the graphics below. 

![Oil Tanker Segmentation 2](https://i.ibb.co/C9vFjWs/Oil-Tanker-Segmentation-2.jpg)

Let’s understand the code for this step in the video below.

**VIDEO**

You will have the masks ready for each instance after running the code explained in the video above. The process of mask generation is summarised in the graphics below:

![Oil Tanker Segmentation 3](https://i.ibb.co/dPHkdhV/Oil-Tanker-Segmentation-3.jpg)

  

You can try to map the code with the image above for better understanding. Next, let’s validate the results obtained after implementing the steps above.

**VIDEO**

As you can see, a new data set has been created which contains the images and the corresponding masks. The original data set has been removed in order to free up space for further processing. In the next segment, you will perform the train-validation split over the new data set. Moreover, the segment will also help you generate the vector annotations in the required MS COCO format.