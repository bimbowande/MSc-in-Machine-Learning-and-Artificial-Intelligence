# Building Datasets

If you are working on an image-based model, the pipeline would be to collate the data from the memory, apply necessary pre-processing steps and transformations to each image and then randomly selecting those images in batch for training the image model. 

Similarly, the pipeline for a text-based model would contain extracting meaningful information from the raw data, cleaning & converting them to tokens, apply necessary pre-processing steps and batching them together for the text model.

The **tf.data API** helps you to build & work with complex input pipelines which allows you to handle large amounts of data and perform complex transformations on them.

To understand the process above, let's create a dataset using the tf.Data API on the MNIST dataset in the next video.

**VIDEO**

The input pipeline starts from importing the data and creating a **dataset** from the data stored in the memory. For this, you can use [tf.data.Dataset.from_tensor_slices()](https://www.tensorflow.org/api_docs/python/tf/data/Dataset#from_tensor_slices), which creates a [tf.data.Dataset](https://www.tensorflow.org/api_docs/python/tf/data/Dataset) the object whose elements are slices of the passed tensors. Once you have created the object, you can transform it by applying different operations to the dataset object. (for example, [Dataset.map()](https://www.tensorflow.org/api_docs/python/tf/data/Dataset#map) or [Dataset.batch()](https://www.tensorflow.org/api_docs/python/tf/data/Dataset#batch)). 

Once we have created the dataset and applied different operations on it, let's move towards the model building pipeline in the next video.

**VIDEO**

Once you have built the dataset, the rest of the process remains the same as you have done while building your custom layers & models. 

Here you have used a **Custom_CNN layer** to build a block that applies both the convolutional operation & BatchNormalisation. You also want to apply a ReLU activation function to the output of both the operation above. Once you have defined the custom layer, you can go ahead and define the architecture of the model.

All three approaches; Sequential models, Functional models & Subclassed models can interact with each other easily. So as part of your subclassing operation, you can use a Sequential or Functional model to define the architecture of your model. 

## Coming Up

In the next segment, you will learn how to do custom training for your model.