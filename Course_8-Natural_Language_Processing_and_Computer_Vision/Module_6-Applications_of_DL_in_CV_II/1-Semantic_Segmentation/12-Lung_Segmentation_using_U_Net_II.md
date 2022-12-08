# Lung Segmentation using U-Net - II

Before proceeding with the model, you must first prepare the data set to suit the requirements of the algorithm. This segment will help you with the steps associated with data preparation. 

The U-Net architecture expects the following conditions to be true before you train a model:

1.  Every source image present in the data set must have a corresponding mask image.
2.  The source image and the corresponding mask image must have the same name to map them adequately.
3.  All the pixels present in the masked images must be mapped to a particular value in order to distinguish one class from another in the image. For example, in the case of lung segmentation, you can encode the pixel values in the binary format as 0 for the background and 1 for the lungs.

Let’s see how to implement this in the upcoming videos.

**VIDEO**

The above video covered the first step towards preparing the data as it dealt with the file names of the mask images. The user-defined function is iterated over all the images to remove the suffix '_mask' from the name of all the images.

Let’s move to the next step in the upcoming video.

**VIDEO**

The above video highlighted that it is not necessary that you always obtain masks for every image in the data set. In such cases, you are left with two options. You can either use an annotation tool to create the mask image or remove those images which do not have the mask image associated with them. As part of this case study, we have dropped the images by comparing the files present in the 'images' and 'masks' folders.

Next, you will have to convert the mask images into the required format for the U-Net library. Let’s learn how to do this in the following video.

**VIDEO**

Since you are dealing with only two classes (lungs and background), each pixel is mapped to either 0 (for background) or 1 (for lungs) in the above video based on the class to which it belongs. This is essential for the machine to distinguish between the two classes during the training and the evaluation steps.

After you have completed the above steps, you are now ready to define the model to perform image segmentation on the images. The next segment will help you with all the steps required to define, train and evaluate the U-Net architecture for the task of lung segmentation.