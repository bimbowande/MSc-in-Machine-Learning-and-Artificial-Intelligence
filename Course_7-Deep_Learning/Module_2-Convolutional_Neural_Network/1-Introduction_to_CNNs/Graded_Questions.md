# Graded Questions

#### Visualizing CNNs

You know that layers in a CNN 'learn' in a hierarchical manner. The initial layers extract low-level features while the layers deep into the network extract more abstract features. Suppose we have trained a 4-layer CNN on a large dataset. After training, we visualise the four layers as given below. Match the layers with what they are expected to have learnt:

![Visualizing CNNs Qn Options ABC](https://i.ibb.co/hDhS37q/Visualizing-CNNs-Qn-Options-ABC.png)

![Visualizing CNNs Qn Option D](https://i.ibb.co/yhvpHPZ/Visualizing-CNNs-Qn-Option-D.png)

- Layer1-(a), Layer2-(b), Layer3-(c), Layer4-(d)

- Layer1-(c), Layer2-(b), Layer3-(a), Layer4-(d)

- Layer1-(b), Layer2-(c), Layer3-(d), Layer4-(a)

- Layer1-(d), Layer2-(a), Layer3-(c), Layer4-(b)

Ans: B. *The projections from each layer show the hierarchical nature of the features in the network. Layer 1 has corners and edges, Layer 2 responds to more complex corners and other edges/ colour conjunctions, Layer 3 captures textures e.g. mesh patterns and Layer 4 shows entire objects with significant pose variation, e.g. dogs.*

Now that you hae come to the end of the session, answer the following graded questions.

#### Pixel range

Qn: What is the range of possible values of each channel of a pixel if we represent each pixel with 5 bits?

- 0 to 255

- 0 to 31

Ans: B. *Since we are representing each pixel by 5 bits, total pixels will be $2^5=32$. So the range is 0-31*
