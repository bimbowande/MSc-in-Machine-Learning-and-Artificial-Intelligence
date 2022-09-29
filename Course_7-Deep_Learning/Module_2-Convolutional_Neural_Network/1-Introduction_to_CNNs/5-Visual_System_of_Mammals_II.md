# Visual System of Mammals - II

You have already seen that every neuron is trained to look at a particular patch in the retina called the receptive field of that neuron. This neuron is designed to look for a particular feature in the image that gives rise to the excitatory region. However, there are multiple questions that should come to your mind: 

-   As different parts are scanned by different neurons, do all the neurons 'see' the same 'features', or are some neurons specialised to 'see' certain features?
-   Every neuron is responsible for finding a ‘feature’ but how does this information translate ahead in the system?

Let's seek answers to some of these questions in the upcoming video.

**VIDEO**

As mentioned in the video, there is a hierarchy in the entire process. The units or the neurons at the initial level do very basic and specific tasks such as picking raw features (for example, horizontal edges) in the image. The subsequent units try to build on top of this to extract more abstract features such as identifying textures and detecting movement. The layers 'higher' in the hierarchy typically aggregate the features in the lower ones.

The following image illustrates the hierarchy in units – the first level extracts low-level features (such as vertical edges) from the image, while the second level calculates the statistical aggregate of the first layer to extract higher-level features (such as texture and colour schemes).

![First Layer to Extract Higher Level Features](https://i.ibb.co/j9tMSc4/First-Layer-to-Extract-Higher-Level-Features.jpg)

Using this idea, if we design a complex network with multiple layers to do image classification (for example), the layers in the network should do something like this:

1.  The first layer extracts raw features like vertical and horizontal edges.
2.  The second layer extracts more abstract features such as textures (using the features extracted by the first layer).
3.  The subsequent layers may identify certain parts of the image such as skin, hair, nose and mouth based on the textures.
4.  Layers further up may identify faces, limbs, etc. 
5.  Finally, the last layer may classify the image as 'human', 'cat', etc.

![Feature Extraction Layers](https://i.ibb.co/hX6CMkR/Feature-Extraction-Layers.jpg)

This divides the entire process into two parts:

1.  Feature extraction
2.  Final task: Classification/regression

![Classification Layers](https://i.ibb.co/FwpzYv0/Classification-Layers.jpg)

Apart from explaining the visual system, the paper also suggested that similar phenomena have been observed in the auditory system and in touch and pressure in the somatosensory system. This suggests that CNN-like architectures can be used for speech processing and analysing signals coming from touch sensors or pressure sensors as well. 

We have already discussed most of the key ideas of the CNN architecture through this paper. Let's have a look at some of the conclusions:

-   Each unit, or neuron, is dedicated to its own receptive field. Thus, every unit is meant to ignore everything other than what is found in its own receptive field.
-   The receptive field of each neuron is almost identical in shape and size.
-   The subsequent layers compute the statistical aggregate of the previous layers of units. This is analogous to the 'pooling layer' in a typical CNN.
-   Inference or the perception of the image happens at various levels of abstraction. The first layer pulls out raw features, and the subsequent layers pull out higher-level features based on the previous features and so on. Finally, the network gets an overall perception of an image in the last layer.

#### Layers in Your Visual Cortex While Driving

CNNs are similar to normal neural networks (MLPs) in that they have layers of neurons arranged sequentially. The paper suggested that the layers are arranged in a hierarchical manner, i.e. the layers further up (towards the right in usual notation) extract more 'abstract' features than the previous layers.

Let's assume that your visual cortex (the region of the brain that receives and processes visual information) has five layers (apart from the input) of neurons. Also, say you are driving, and in the process, you are doing object detection -  i.e. detecting the area where an object is on the road or footpath (a pedestrian, a car, a traffic signal, a tree etc.) and recognising it:

![Layers in Your Visual Cortex While Driving](https://i.ibb.co/6ttyVHf/Layers-in-Your-Visual-Cortex-While-Driving.jpg)

Qn: Which of the following statements can be true? Mark all correct possibilities:

- The first layer extracts basic features from the image, such as edges, while the second extracts textures, colour patterns, etc.

- The fourth layer may be detecting the area (the rectangular box) where an object is located, while the fifth (last) layer classifies it into one of the categories (person, car etc.)

- The second layer may be classifying the object into one of the categories (person, car etc.)

Ans: A & B. *The initial layers extract basic patterns, while the latter ones extract higher-level patterns. Classification of the object can only be done after finding where it is located.*

The CNN architecture tries to replicate this entire process in its architecture. However, before discussing the components of CNN, it is also essential to thoroughly understand the type of data you will deal with. The next segment will help you in understanding how the visual data is stored in the images.