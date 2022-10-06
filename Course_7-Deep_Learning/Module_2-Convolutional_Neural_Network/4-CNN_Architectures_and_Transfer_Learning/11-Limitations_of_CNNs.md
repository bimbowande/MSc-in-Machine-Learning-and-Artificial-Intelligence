# Limitations of CNNs

The CNN framework has been a great addition to the pool of models associated with deep learning. They are the reasons why deep learning is so popular today. The CNN models revolutionised the process of dealing with visual data. However, these models are still far from reaching the level of the visual system of mammals. This segment will help you in understanding the limits of the model.

Apart from being the black-box model, other limitations of CNNs were highlighted by Geoffrey Hinton, one of the pioneers of deep learning, in his keynote speech at the [AAAI conference](https://www.aaai.org/Conferences/AAAI/aaai.php). It is one of the main AI conferences. We will not be discussing them in detail, as it would require in-depth knowledge of different deep learning concepts. However, this would provide you a basic understanding of the shortcomings of the model. So, let’s get started with them one by one.

1.  **Inability to deal with all the local transformations**

You learnt that the CNN architecture uses the pooling operation to overcome different variations such as translation and rotation. However, the model is only able to deal with the translational variance effectively. It does not perform well if there is a change in the viewpoint. This makes the network inefficient when compared to the visual system of mammals, as humans can identify objects viewed from different angles or distances. 

The problem can be solved, but the method used is not always efficient. Developers use a technique called ‘data augmentation’, where they prepare multiple copies of the same image by introducing different variations through cropping, rotating or flipping the image for the model to train on them. This provides different viewpoints for the network to learn but still leaves the model exposed to numerous other variations possible. 

2.  **Loss of spatial information in the deeper layers**

CNNs follow a hierarchical order to extract features from an image. The basic features, such as edges and corners, are combined to make higher-level features, such as shapes and objects. The network uses these high-level features to identify different objects present in the image. For example, the network would identify a face in the image if it had features, such as a couple of eyes, the basic structure of a face, a nose and lips. If you recall, the VGGNet framework used 4,096 different features to classify images. But the spatial relationship between the features is lost after flattening. Hence, the network does not account for the position of these features in the image while calculating the probabilities for each class. For example, both the images given below have the basic features of a face. Therefore, the network would classify both images as faces even though the second one is a distorted figure.

![Loss of spatial information in the deeper layers](https://i.ibb.co/PCzCv47/Loss-of-spatial-information-in-the-deeper-layers.jpg)

This suggests that the network does not account for the structure or the arrangement of the features; it only checks for its presence in the image.

3.  **Adversarial attacks**

It is quite evident from the aforementioned case that the visual system in mammals and the CNN architecture are very different from each other. Humans have a general sense of the objects; however, the learning in a CNN is limited to the data provided for training. This gives rise to another problem of adversarial attacks.

It has been seen that with the introduction of slight variation or noise in an image, CNNs recognise the object as something completely different from the previous result. The image given below summarises this problem.

![Adversarial attacks](https://i.ibb.co/mTTpcCF/Adversarial-attacks.jpg)

_Source: PyTorch_

As you can see, the object that was initially classified as ‘panda’ has changed to ‘gibbon’ with the introduction of noise in the image. Visually, the images are still the same for a human but completely different for a machine. This poses a threat to a lot of different applications of CNNs. A few real-life examples have been mentioned below:

-   The adversarial attacks can make traffic signs invisible to a neural network. This was an [experiment](https://arxiv.org/pdf/1707.08945.pdf) conducted by researchers at Samsung and Universities of Washington, Michigan and UC Berkeley. This is a major drawback for self-driving cars, as it could impact the safety of the person, which is always the key concern.

![Adversarial attacks Stop Sign](https://i.ibb.co/LYzgJfq/Adversarial-attacks-Stop-Sign.jpg)_

_Source:_ [_Robust Physical-World Attacks on Deep Learning Visual Classification_](https://arxiv.org/pdf/1707.08945.pdf)

-   In another [experiment](https://www.cs.cmu.edu/~sbhagava/papers/face-rec-ccs16.pdf) conducted by researchers at Carnegie Mellon University, it was shown that the facial recognition systems that work on neural networks can be fooled by individuals wearing a special pair of glasses. You can only imagine the amount of risk that it poses to security systems.

![Adversarial attacks Faces](https://i.ibb.co/5jBd7QF/Adversarial-attacks-Faces.jpg)

_Source: [_Accessorize to_ a Crime: Real and Stealthy Attacks on State-of-the-Art Face Recognition](https://www.cs.cmu.edu/~sbhagava/papers/face-rec-ccs16.pdf)_

-   This element was also explored by [Google](https://arxiv.org/pdf/1712.09665.pdf).  Researchers added stickers to the input image and then ran the model. Surprisingly, it impacted the results quite significantly, as illustrated in the image given below.

![Adversarial attacks Incorrect Labels](https://i.ibb.co/3MPkYKR/Adversarial-attacks-Incorrect-Labels.jpg)

_Source: [Adversarial Patch](https://arxiv.org/pdf/1712.09665.pdf)_

Some other smaller drawbacks associated with the model are mentioned below:

-   The CNN model is heavily reliant on the kind of data that is fed to the network for training. It is true that the CNN model is as good as the data that it is trained on. As you read above, the network requires large amounts of data (with multiple variations) to perform accurately on an unseen image.
-   Due to a large amount of data and the operations involved in the process, you require GPUs and other resources to work with the CNNs. Without them, the training and deployment would be extremely slow to use in any case.

The next segment will summarise your learnings from the session.

## Additional reading

You can listen to Geoffrey Hinton’s talk '[What is wrong with convolutional neural nets?](https://www.youtube.com/watch?v=rTawFwUvnLE)' for much more clarity on the limitations of CNNs.