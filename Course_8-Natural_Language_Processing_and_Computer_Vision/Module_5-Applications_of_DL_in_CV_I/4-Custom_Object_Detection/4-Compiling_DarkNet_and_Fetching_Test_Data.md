# Compiling DarkNet and Fetching Test Data

In the previous segment, you learnt how to fetch pre-trained weights. In this segment, you will learn how to divide the data that you fetched into training and validation data. You are already well-versed with this step of the code, as you have performed it for many other deep learning and machine learning models. Let’s watch the upcoming video to learn how to perform this step.

**VIDEO**

In order to split the data, you will require three libraries. For this, you can import the required libraries using the following code:

```python
from sklearn.model_selection import train_test_split
import pandas as pd 
import os 
```

  
After importing the libraries, mention the path to the data and create a list for the files, as shown below.

```python
PATH = 'images/'
list_img=[img for img in os.listdir(PATH) if img.endswith('.jpg')==True]
 
path_img=[]
 
for i in range (len(list_img)):
    path_img.append(PATH+list_img[i])
    
df=pd.DataFrame(path_img)
 
# split 
data_train, data_test, labels_train, labels_test = train_test_split(df[0], df.index, test_size=0.20, random_state=42)
```

  
Now, take the split data and save it in the respective files, as shown below.

```python
train_idx=list(data_train.index)
test_idx=list(data_test.index)
    
# relative path to the binary 
relpath = "custom_data/"
backup_path = "/content/drive/MyDrive/my_model/"
 
# Train file
# Open a file with access mode 'a'
with open("training_data.txt", "a") as file_object:
  for i in range(len(train_idx)):
    file_object.write(relpath+data_train[train_idx[i]]+"\n")   
 
with open("validation_data.txt", "a") as file_object:
  for i in range(len(test_idx)):
    file_object.write(relpath+data_test[test_idx[i]]+"\n")
```

To reiterate, do not forget to create a backup of your files using following the code snippet:

```python
%cp training_data.txt ../../drive/MyDrive/my_model/
%cp validation_data.txt ../../drive/MyDrive/my_model/
```

Once you have split and saved the data into the respective files, all the changes required to be made in this custom file are completed. You can now compile the DarkNet project and fetch the training data. Let’s watch the next video to learn more about this.

**VIDEO**

You can simply compile the DarkNet project in the following two simple lines of code:

```python
# enter DarkNet directory
%cd ..
 
# compile the DarkNet project
!make -j4
```

Once the DarkNet project is compiled, you need to fetch the testing data from the coco data set using the following command:

```python
!./darknet detector test cfg/coco.data cfg/yolov4.cfg customization/yolov4.weights data/person.jpg
```

Now, confirm the data upload using the following code:

```python
from google.colab.patches import cv2_imshow
test_image = cv2.imread("data/person.jpg")
cv2_imshow(test_image)
```

With this, you have performed all the steps leading to the model training part. In the next segment, you will learn how to train this custom model.