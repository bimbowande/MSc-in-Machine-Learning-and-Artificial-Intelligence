# Visual System of Mammals - I

We had mentioned that the architecture of CNNs is motivated by the visual system of mammals. In this segment, we will discuss an influential paper named ‘[Receptive Field for Single Neurons in the Cat’s Striate Cortex](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1363130/pdf/jphysiol01298-0128.pdf)’ published by Hubel and Wiesel. The reason for this is that a lot of components of the CNN architecture were inspired by this research.

This was basically a bunch of experiments conducted to understand a cat’s visual system. In the experiments, spots of light (of various shapes and sizes) were made to fall on the retina of a cat and, using an appropriate mechanism, the response of the neurons in the cat's retina was recorded. This provided a way to observe which types of spots make some particular neurons 'fire', how groups of neurons respond to spots of certain shapes, etc.

Let’s look at some of the findings of Hubel and Wiesel made in this paper.

**VIDEO**

The video summarised all the important observations made in the study:

-   Each neuron in the retina focuses on one part of the image and that part of the image is called the **receptive field of that neuron**. The following figure shows a certain region of the receptive field of a cat. 

![Field of a Nueron](https://i.ibb.co/jgkTyDy/Field-of-a-nueron.jpg)

-   The receptive fields of all neurons are almost **identical** in shape and size.
-   The receptive field has **excitatory** and **inhibitory** **regions**. The excitatory region (denoted by the triangular marks) forms the **key feature or the element** that the neuron is trained to look for and the inhibitory region is like the **background** (marked by the crosses). 
-   The neurons only ‘fire’ when there is a **contrast** between the excitatory and the inhibitory regions. If we splash light over the excitatory and inhibitory regions together, the neurons do not ‘fire’ (respond) because of no contrast between them. If we splash light just over the excitatory region, neurons respond because of the contrast. This helps us identify a given feature in the receptive field of a particular neuron.

![Receptive Field of a Particular Neuron](https://i.ibb.co/5jZc8Bh/Receptive-Field-of-a-Particular-Neuron.jpg)

-   The strength of the response is proportional to the summation over only the excitatory region (not the inhibitory region). Instead of looking at the response from individual neurons, the response from multiple neurons is aggregated using some statistical measure (sum, average, etc.). This concept is replicated as a pooling layer in CNNs which corresponds to this observation.

#### Receptive Field

Qn: Each neuron in the retina is trained to 'look at':

- The entire image

- A particular patch (region) of the image

Ans: B. *Each neuron is trained to look at only a certain patch of the image. This patch is called the receptive field of that neuron.*

#### Understanding the Visual System of Mammals

Qn: The excitatory and the inhibitory regions are:

- Regions in the receptive field which invoke a ‘response’ from all the neurons

- Regions in the receptive field which invoke a ‘response’ from the neurons trained to focus on that receptive field

- Regions in the input image which invoke a ‘response’ from all the neurons

Ans: B. *All neurons do not respond to light falling on a receptive field, only the ones trained to focus on that receptive field do.*

In the next segment, we will study some more observations from this study that influenced the CNN architecture.

## Additional Reading

-   The paper '[Receptive Field for Single Neurons in the Cat’s Striate Cortex](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1363130/pdf/jphysiol01298-0128.pdf)' by Hubel and Wiesel.