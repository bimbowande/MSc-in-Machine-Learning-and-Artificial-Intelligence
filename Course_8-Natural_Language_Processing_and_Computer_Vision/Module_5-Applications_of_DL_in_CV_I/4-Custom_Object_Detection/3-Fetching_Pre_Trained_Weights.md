# Fetching Pre-Trained Weights

So far, you have learnt how to import the required library and load the DarkNet project for your model. The next step is to fetch the pre-trained weights in order to test the model. Let’s watch the next video to learn how to do this.

**VIDEO**

As you saw in the video above, you will be required to create a new directory where you can upload the pre-trained weights. You can do this using the following code:

```python
# create a new directory and enter inside it
%mkdir customization
%cd customization

# fetch the pre-trained weights from the GitHub link
!wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights
!wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.conv.137
```

After fetching the pre-trained weights for both testing and training your model, you need to save them in your drive. The testing weights will be used later once the model is built and trained. You can save the weights as follows:

```python
# copy and save the testing weights in your drive
%cp yolov4.weights ../../drive/MyDrive/my_model/
```

Next, you need to create a custom configuration file as follows:

```python
%cp ../cfg/yolov4.cfg .
```

After creating the customisation directory, open it by double-clicking on ‘yolov4.cfg’ on the left panel. Since this is a transfer learning task, you need to change the weights. After opening your directory, make the following changes:

1.  Line 3: A subdivision is the number of tiles each image is cut into for GPU processing. Change this from subdivisions=8 to subdivisions=64.  
     
2.  Line 7: Change the resized image width from width=608 to width=416.  
     
3.  Line 8: Change the resized image height from height=608 to height=416.  
     
4.  Line 19: max_batches is equal to classes, i.e., 2,000 but it should not less than the number of training images or less than 6,000. Change this from max_batches = 500500 to max_batches = 4000 for our two classes.  
     
5.  Line 21: Change line steps to 80% and 90% of max_batches. We use a single step for memory efficiency. Change this from steps=400000, 450000 to steps=3200.

Also, change the last set of filters before each output layer as follows:

-   Line 961, 1049, 1137: Change this from filters=255 to filters=21. The rule is (classes + 5)x3 in the 3 convolutional layers before each YOLO layer. Note that it only has to be the last convolutional layer before each of the YOLO layers. 

  
Change the number of classes in each output layer as follows:

-   Line 968, 1056, 1144: Change this from classes=80 to classes=2.

Finally, press Ctrl+S to save the edited .cfg file.

Note: The ‘max_batches’ entry is set to 4,000 based on the YOLO guidelines. However, this will result in approximately 10h of training. Since it was observed empirically that the best network weights are obtained before 2,000 epochs, it is recommended to change the following to:

-   max_batches = 2000
-   steps = 1600

Once you have saved the changes, you can visualise and back the configuration using the following code:

```python
# visualise the configuration file
!cat yolov4.cfg

# backup the configuration file
%cp yolov4.cfg ../../drive/MyDrive/my_model/
```

After making the changes in the customisation file and saving it, the next step is to fetch the training data. Note that earlier, you fetched and saved the training and test weights. Now, you will fetch and save the training data. Let’s watch the next video to learn more about it.

**VIDEO**

As you saw in the video above, in the next step, you need to perform the following steps:

1.  Create the directories for custom data consisting of images and labels, as shown below.
    
```python
%cd ../
%mkdir custom_data
%cd custom_data
%mkdir images
%mkdir labels
```
    
2.  Download the data using this link: [Training Data](https://www.kaggle.com/saurah403/face-mask-detectionimages-with-yolo-format/download). After downloading the data, upload it to your drive and do not forget to copy the path to the folder containing the training data, as shown in the image below.
    
    ![Colab Copy Path](https://i.ibb.co/VYJnj4n/Colab-Copy-Path.jpg)
    
3.  Upload the data to your drive and fetch the data as follows:
    
```python
    %cd ./images/
    %cp /content/drive/MyDrive/object_detection/data/archive.zip .
    !unzip archive.zip -d .
    %rm archive.zip
    
    %mv ./images/* . 
    %rm -r images/
```
    
    Note: Do not forget to change the path to the training data in the second line of code.  
     
    
4.  Check the image extensions and convert them into the JPG format wherever required as follows:
    
```python
    !find . -type f | awk -F. '!a[$NF]++{print $NF}'
    
    # You will find .png, .jpg, .txt and .jpeg files. Out of these 4 types, .jpeg and .jpg are acceptable but you will be required to convert .png to .jpg
    from glob import glob                                                           
    pngs = glob('./*.png')
     
    for j in pngs:
        img = cv2.imread(j)
        cv2.imwrite(j[:-3] + 'jpg', img)
    
    # remove all the .png files
    %rm *.png 
```
    
5.  Populate the directories and labels using the following command:
    
```python
    # copy the text files to labels folder as they have no significance in the image folder
    %cp *.txt ../labels/
```
    
6.  Create auxiliary files for transfer learning. You will need four files for training, validation, class names and class data. You can create these files using the following commands:
    
```python
    %cd ../
    !touch training_data.txt
    !touch validation_data.txt
    !touch face_mask_classes.names
    !touch face_mask.data
```
    
7.  Now, you can write to these files using the 'echo' command, as shown below:
    
```python
    !echo "no face mask" >> face_mask_classes.names
    !echo "face mask" >> face_mask_classes.names
    
    
    Configure and verify the file names as follows:
    !echo "classes = 2" >> face_mask.data
    !echo "train = custom_data/training_data.txt" >> face_mask.data
    !echo "valid = custom_data/validation_data.txt" >> face_mask.data
    !echo "names = custom_data/face_mask_classes.names" >> face_mask.data
    !echo "backup = backup/" >> face_mask.data
    
    # verify the configures files
    !head face_mask.data
```
    
8.  Finally, do not forget to create a backup of the file in your my_model directory using the following code.
    
```python
    %cp face_mask.data ../../drive/MyDrive/my_model/
    %cp face_mask_classes.names ../../drive/MyDrive/my_model/
    
```

Now that you have successfully fetched and saved your data, the next step is to split the data into training and validation sets. You will learn how to do the same in the upcoming segment.