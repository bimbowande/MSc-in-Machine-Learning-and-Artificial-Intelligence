# Starter Code Walkthrough

In the previous segments, you have been introduced to the data, different model architectures, generator functions and also the information flow of the fit_generator. The following starter code walkthrough will help you in understanding the modelling process the skeleton of the project code. Please download the starter code from the following link.

Download [Neural Nets Project Starter Code](Neural_Networks_Project_Gesture_Recognition_Starter_Code.ipynb)

**VIDEO**

You have seen how the custom generator function works with the yield statement. A custom generator would help you in creating a batch of any kind of data, for example, text data which is not readily available with keras.

An interesting thing to note here is the use of the infinite while loop. It is there in place so that the generator is always ready to yield a batch once next() is called once it is called at the start of training. Even after one pass over the data is completed (after the for loop is completed and the batch for the remainder datapoints is yielded), upon the subsequent next() call (at the start of the next epoch), the processing starts from the command 't=np.random.permuatation(folder_list)'. In this way, the generator requires very less memory while training. You have been provided with the skeleton code for the custom generator and you have to experiment your model with the following:

1.  number of images to be taken per video/sequence
2.  cropping the images
3.  resizing the images
4.  normalizing the images

Snehansu has also pointed out some of the tips and tricks like keeping the aspect ratio of all the images the same and others to help you out in deciding the above parameters. Apart from these, you have to complete the rest of the code of custom generator as mentioned in the lecture.

Let's now look at the next lecture in which Snehansu walks through the rest of the code.

**VIDEO**

By now, you have understood how the different blocks of code work. This project gives you an exposure to the real-world data. It would require you to brainstorm and try out a lot of experiments to get the correct values of parameters you need to play around with as well as the model architecture so as to get the best results. The Keras documentation should help you in figuring this bit out.

## **Goals of this Project**

In this project, you will build a model to recognise 5 hand gestures. The starter code has been shared with you above. Before you start working on the mode, let's see the suggestions Snehansu has to finish the project successfully.

**VIDEO**

You need to accomplish the following in the project:

1.  **Generator:**  The generator should be able to take a batch of videos as input without any error. Steps like cropping, resizing and normalization should be performed successfully.
    
2.  **Model:** Develop a model that is able to train without any errors which will be judged on the total number of parameters (as the inference(prediction) time should be less) and the accuracy achieved. As suggested by Snehansu, start training on a small amount of data and then proceed further.
    
3.  **Write up:** This should contain the detailed procedure followed in choosing the final model. The write up should start with the reason for choosing the base model, then highlight the reasons and metrics taken into consideration to modify and experiment to arrive at the final model. 

Download [Sample Write-Up](Sample_Write_Up.docx)

You’ll be evaluated on the following submission:

Submit a zip folder containing the jupyter notebook having the final model, the final .h5 file and the write-up. The .h5 file will be used to calculate the accuracy on the test data.

There are certain things you should keep in mind before proceeding further:

1.  Whenever you modify your model, run the notebook from the beginning. This is to reset the initialisations and the generator.
2.  To check the GPU usage, execute 'nvidia-smi' on the terminal.