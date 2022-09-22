# Graded Questions

The following questions are graded. All the best!

#### Feedforward

Qn: Consider a neural network with five hidden layers. Choose the ones that are correct in the feedforward process.

- The output of the second hidden layer can be calculated only after the output of the third hidden layer is calculated in one feedforward pass.

- The output of the third hidden layer can be calculated only after the output of the second hidden layer is calculated in one feedforward pass.

- The output of the third hidden layer can be calculated only after the output of the fourth hidden layer is calculated in one feedforward pass.

- The output of the fifth hidden layer can be calculated only after the output of the second hidden layer is calculated in one feedforward pass.

Ans: B & D. *In feedforward, the output of layer 'l' can be calculated only after the calculation of the output of all the 'l-1' layers. Therefore, the output of the third hidden layer can be calculated only after the output of the second hidden layer in one feedforward pass.*

Qn: Consider a neural network with five hidden layers. You send in an input batch of 20 data points. What will be the dimension of the output matrix of the fourth hidden layer if it has 12 neurons?

- (20, 1)

- (12, 20)

- (12, 1)

- (20, 12)

Ans: B. *Dimension = (number of neurons in the layer, size of the batch). Therefore, the answer will be (12, 20).*

Qn: Consider a neural network with five hidden layers. You send in an input batch of 20 data points. How will you denote the weight matrix between the hidden layers 4 and 5?

- $W^4$

- $W^5$

Ans: B. *$W^l$ is the weight matrix between the layers l and l-1.*

Qn: Consider a neural network with five hidden layers. You send in an input batch of 20 data points. The weight matrix W3 has the dimension (18, 12). How many neurons are present in the hidden layer 2?

Note: For all the questions, you will not be taking into account the transpose of weight matrix as mentioned earlier. The formula used will be z=w.x+b.

- 18

- 12

Ans: B. *Matrix dimension = (number of neurons in the layer in layer 'l-1', number of neurons in layer 'l')*

In this session, you learnt about feedforward neural networks and computed the predicted output of the model. However, these models are not 100% efficient and incur some losses.

In the next session, you will gain an understanding of loss functions in neural networks and learn how to minimise them. You will also be introduced to a very interesting and important concept in the world of neural networks, which is backpropagation.