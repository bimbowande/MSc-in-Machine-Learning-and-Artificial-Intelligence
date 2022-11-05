# Model Training

So far, you have performed multiple steps involved in setting up the environment, fetching weights and data, and customising the DarkNet project. In this segment, you will learn how to train this custom YOLO model. Let’s watch the next video to get started.

**VIDEO**

Note: In the video, the speaker says 5 hours for training, it will be 10 hours instead.

In order to train your custom model, you need to create some directories and remove the unwanted ones. You can do this using the following code:

```python
# remove the backup in the DarkNet directory
%rm -r /content/darknet/backup

# create a backup directory for model training in my_model
%mkdir ../drive/MyDrive/my_model/backup/
!ln -s /content/drive/MyDrive/my_model/backup/ /content/darknet/
```

Then you can train your model using the following code:

```python
!./darknet detector train custom_data/face_mask.data customization/yolov4.cfg customization/yolov4.conv.137 -map -dont_show
```

The training command consists of the following two auxiliary parameters:

1.  **map**: If this flag is set, this generates a raster plot/graph of the loss and the mean average precision.
2.  **dont_show**: If this flag is set, this prevents attempts to display the progress chart that may cause disruptions in the notebook environment

Note that it will take around 10 hours for the model to train. Additionally, while training the model you will be able to analyse a **progress chart**. This chart is nothing but an image file (PNG format) generated periodically to report the latest mean average precision (mAP) vs the loss value for each iteration. It can be found inside the DarkNet directory. You may download this image to check the training progress of the model.

You can also check the **log file**. This file may lag at times temporarily, but the process continues to run in the background.
  
If your process faces a **disconnection/timeout**, check your backup folder in Google Drive for which you created the symbolic link. You will find several weight files, including one generated for every 1,000 iterations, one with the best weights computed (highest mAP and not lowest Loss), and one with the latest weights before timeout or training completion. You may choose to reconnect the notebook and start off at the point where you stopped, by running the following code:

```python
!./darknet detector train custom_data/face_mask.data customization/yolov4.cfg /content/drive/MyDrive/my_model/backup/yolov4_last.weights -map -dont_show
```

Once your training process is complete, do not forget to download the following files:

-   The best weights file
    -   MyDrive/my_model/backup/yolov4_best.weights
-   The configuration 
    -   file /content/darknet/customization/yolov4.cfg
-   The summary chart
    -   image file /content/darknet/chart_yolov4.png

Once your model is trained and you have downloaded the required files, you can proceed to a new notebook and deploy the model to predict the presence of facemasks on human faces. Let’s proceed to the next segment to learn how to deploy a YOLO custom model.