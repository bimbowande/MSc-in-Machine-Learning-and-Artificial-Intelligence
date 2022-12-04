# Oil Tanker Segmentation - III

You have generated the masks for each image in the previous segment. Now, you will see how to split the data into training and validation sets. Moreover, the segment will also teach how to generate the vector annotations for both sets in accordance with the MS COCO format.

Let’s first split the dataset into training and validation sets in the ratio 9:1 in the upcoming video.

**VIDEO**

The training and validation sets have been generated using the train_test_split function. Each set has been stored in a separate folder as the path must be provided separately during the model training process. 

To perform the task of instance segmentation, Mask R-CNN expects the raw images along with the vector annotations in the MS COCO compatible format. Let’s first understand the components of the JSON-type annotation file in the video below.

**VIDEO**

The video highlighted the five blocks of information present in the annotation file:

-   Info
-   License
-   Image: Stores information about the images like file name, height, width, ID, etc.
-   Categories: Contains information about all the class labels and the associated ID.
-   Annotation: Information about the masks associated with an image.

The required file for the Mask R-CNN framework can be downloaded from the GitHub repository shared by Georgios. However, the attributes associated with the file must be updated according to the problem at hand. The global variables for the categories section (category labels and the associated ID and color) have been declared in the video above. They will be later used to update the JSON file.

#### Oil Tanker Segmentation

Qn: Based on the specifications provided in the video above, what are the colors mapped to each label in the chip?

- Background: White, Oil Tanker: Black

- Background: None, Oil Tanker: White

- Background: Black, Oil Tanker: White

Ans: C. *Oil tanks have been mapped to (255, 255, 255) and the background is mapped to (0, 0, 0).*

#### Mask R-CNN

Qn: Which of the following sections stores the information about the different classes that could be present in the images?

- Info

- License

- Image

- Categories

- Annotation

Ans: D. *Contains information about all the class labels and the associated ID.*

Let’s move to the next video to define the other attributes present in the JSON file.

**VIDEO**

The video covers the function that will be used to update the ‘image’ and the ‘annotation’ section of the JSON file. The function expects the user to provide the directory path of the masks, image names, image IDs and a tuple that stores the color associated with the background class.

Let us now run the function to obtain the annotation files for the training and the validation sets.

**VIDEO**

The video shows how the MS COCO template can be loaded in the Colab environment. Post that, you can use the defined attributes and functions to update the categories, image and annotation sections of the JSON file for both the training and the validation set.

Now, you have all the required inputs to proceed with the task of model building. The next segment will help you with the step of model definition.
