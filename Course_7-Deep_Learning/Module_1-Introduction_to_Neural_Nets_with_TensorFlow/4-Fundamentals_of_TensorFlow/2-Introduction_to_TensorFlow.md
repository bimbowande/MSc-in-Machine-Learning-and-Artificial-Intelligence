# Introduction to TensorFlow

TensorFlow is an **open-source platform** for developing end-to-end machine learning (ML) solutions. The TensorFlow platform contains services such as TensorFlow.js, TensorFlow lite and TensorFlow Extended, which are used to develop applications for browsers, mobile platforms and large production environments, respectively. 

TensorFlow in itself has everything one might need to build a solution and deploy it on different platforms. One part of the complete TensorFlow environment is the **TensorFlow machine learning library**, which is the topic of this session. 

TensorFlow is a **deep learning library** developed by **Google**. It is used widely in the industry for several different applications. Some of these applications include smart text in Gmail, Google Translate and Google Lens. Now, in the forthcoming video, you will learn about TensorFlow and its features from Avishek.

**VIDEO**

## How does TensorFlow help in deep learning?

1.  **Easy API to design complex models:** The developers of TensorFlow created a [TensorFlow playground](https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=circle&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=4,2&seed=0.50000&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false), which helps with visualising the performance of the neural network model. When you visit the app, focus on model performance by changing the data set and the depth of the neural network, which is defined by the number of hidden layers. You can permute numerous options available on the page, such as the activation function, learning rate, regularisation, different types of inputs and different types of data sets.  
      
    **Activity**  
    Open TensorFlow playground, and to get started, use a simple data set and the default neural network configuration, and press play. On the right-hand side, you will notice that the model is trying to separate the data points, and at the top, you will also notice the overall test and train error. Observe the number of epochs (another word for iterations) that the model takes to create the separation boundary.   
      
    Now, increase data complexity by choosing a different data set. Build a model by varying only the depth and the number of neurons of the network to separate the complex data set.  
      
    You can perform the following experiments in TensorFlow Playground. Let these simulations run for 400 epochs and note the decision boundaries that are created. 
    1.  Input data: Concentric  
        Number of hidden layers: 2   
        Neurons in the first layer: 4.  
        Neurons in the second layer: 2  
         
    2.  Input data: spiral   
        Number of hidden layers: 2   
        Neurons in the first layer: 4.  
        Neurons in the second layer: 2  
         
    3.  Input data: spiral   
        Number of hidden layers: 4   
        Neurons in all the layers: 8  
          
        Deep neural networks are better at learning trends and patterns in complex data. The TensorFlow API provides the ability to build such deep models with only a few lines of code, making the building process extremely easy.   
         
2.  **High-speed processing of data**: Although deep learning has great advantages, it is associated with certain challenges. Deep learning algorithms need a lot of data for training, which means the algorithms must be fast so that they can train on huge amounts of data in an acceptable amount of time. Consider the ImageNet data set. It has approximately 14 million images, with a training data set of about 136 GB, which can be used to train neural network models. TensorFlow provides the ability to access specialised hardware that can increase the computation speed significantly.

TensorFlow increases the training speed using specialised hardware, that is, using GPUs and TPUs for processing. In the forthcoming video, you will learn about the computational capabilities of different hardware that are available for processing.

**VIDEO**

Let us revise the different processing units in TensorFlow:

1.  **CPU or central processing unit**  
    It is the most commonly used processing hardware. CPUs are designed in a way that they can perform different types of computations quickly. Usually, CPUs have extremely high clock speeds or can perform serial calculations extremely fast. You can think of a CPU as a supercar that you use for commuting from your house to the grocery shop where you buy groceries. This supercar can help you make trips to the store extremely quickly.   
     
2.  **GPU or graphics processing unit**  
    GPUs are general-purpose computing devices. Compared with CPUs, GPUs have slower clock speeds, but they are efficient at parallel computing. Although GPUs are used extensively in the gaming industry, they are quite efficient at data processing as well. You can think of them as using a goods truck to go to the grocery store. Even though it would take longer than using a supercar for each trip, it can carry much more goods per trip, making it much faster than a CPU on an overall basis.   
     
3.  **TPU or tensor processing unit**  
    A TPU is a specialised device that is developed by Google for processing data that is in the form of tensors. It cannot be used for any other processing needs. Since TPUs are developed specifically for processing data in the tensor format, they are extremely fast. A TPU is similar to a special conveyor belt connecting your house to the grocery store. Even if it cannot be used to do anything other than getting groceries, it is the fastest possible way. You can refer to the Google presentation [here](http://storage.googleapis.com/nexttpu/index.html) to better understand how CPU, GPU and TPU differ. Please visit the animations page as well.

In the earlier video, you saw that for a specific neural network ResNet50, with nearly 23 million training parameters, a cloud of TPUs is almost 200 times better than a single GPU. So, being able to process a lot of data at a high speed makes TensorFlow a good fit for deep learning.

Now, answer these questions based on your learning from this segment.

#### Processing Devices

Qn: Which of these statements about processing devices is true? (Note: More than one option may be correct.)

- TensorFlow can access CPUs, GPUs and TPUs for computation purposes.

- A GPU is a general-purpose computing device.

- A TPU can be used for gaming.

- CPUs are the fastest in terms of processing tensors.

Ans: A & B. *TensorFlow can access all three devices. A GPU can be used for training, gaming, image processing, etc.*

#### Non-Linear learning

Qn: What does a neural network need to capture the complex, nonlinear nature of data?  
(Note: More than one option may be correct.)

- Increasing the number of hidden layers

- Increasing the number of inputs

- Nonlinear activation functions

- Data preprocessing to make it linear

Ans: A & C. *The depth of a neural network increases the nonlinearity of the model. To capture nonlinear data, the activation function also needs to be nonlinear.*

The features of TensorFlow make it a useful library for ML. In the upcoming segments, you will explore all these features in detail.