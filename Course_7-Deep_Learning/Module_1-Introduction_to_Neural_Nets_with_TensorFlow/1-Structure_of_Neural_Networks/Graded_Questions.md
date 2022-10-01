# Graded Questions

The following questions are graded. All the best!

#### Perceptron

Qn: Suppose we take all the weights and biases in a perceptron and multiply them by a positive constant, c > 0. The perceptron uses the following step function as the activation function:
$$\large{\begin{cases}y=1;\text{ if }x>0\\\\y=−1;\text{ if }x<=0\end{cases}}$$
Will the output of the perceptron change (compared to the vanilla perceptron without any positive constant c)?

- Yes

- No

- It depends on 'c'.

- It depends on the inputs to the perceptron.

Ans: B. *The cumulative input into the perceptron is $w_1x_1+w_2x_2+\dots+w_kx_k+b$. If we multiply all the weights and biases by a positive constant, $c>0$, it becomes $c(w_1x_1+w_2x_2+\dots+w_kx_k+b)$ but the $sign(w_1x_1+w_2x_2+\dots+w_kx_k+b)=sign(c(w_1x_1+w_2x_2+\dots+w_kx_k+b))$ as $c>0$. hence, the output will not change.*

#### Basic Hyperparameters of Neural network

Qn: The hyperparameters in a neural network are (mark all that apply):

- Number of layers

- Number of neurons in each layer

- Weights

- Biases

- The activation function (assume it is the same for each neuron)

Ans: A, B & E. *Weights and biases are to be found using training. Hyperparameters are given as inputs to the learning algorithm which finds out the optimal parameters (weights and biases).*

#### Inputs

Qn: For an RGB image as input having 32 x 32 pixels, you want to classify it into a dog, cat, bird or none of the above. What will be the number of neurons in the input layer?

- 3072

- 1024

- 32

- 3

Ans: A. *A black white 32 x 32 image would have 32x32 input neurons. The RGB image has 3 channels. Hence 32x32x3 = 3072 input neurons.*

#### Outputs

Qn: For an RGB image as input having 32 x 32 pixels, you want to classify it into a dog, cat, bird or none of the above. What will be the number of neurons in the output layer?

- 3

- 4

- 2

- 1

Ans: B. *There are 4 classes we have to classify - 1. dog 2.cat 3.bird 4.none of the above. Hence, 4 output neurons.*

#### Output Layer

Qn: For an RGB image as input having 32 x 32 pixels, you want to classify it into a dog, cat, bird or none of the above. Would you use a sigmoid/ softmax layer as the output layer?

- Sigmoid

- Softmax

Ans: B. *Since there are 4 classes, we shall use a softmax layer.*

#### Notations

Qn: How would you denote the output of the third hidden layer?

- $z^3$

- $h^3$

- $z_3$

- $h_3$

Ans: B. *The output of the hidden layer is defined by $h$. Superscript denotes the layer number.*

Qn: How would you denote the weight which connects the 6th neuron of hidden layer 3 to the 8th neuron of hidden layer 4?

- $w^4_{68}$

- $w^4_{86}$

- $w^3_{68}$

- $w^3_{86}$

Ans: A. *The superscript in the weight is layer l, where weight is present between layer ‘l-1’ and layer 'l'. The subscript is denoted by the (l-1, l). Therefore, the superscript between the third and fourth layer will be 4, the superscript of connection between the sixth and eighth neuron will be 68. Hence, the answer will be $w^4_{68}$.*

#### Number of Interconnections

Qn: We have a hidden layer number 3 with 11 neurons and the hidden layer number 4 with 18 neurons. Also, these hidden layers are densely connected. How many connections will be present? Note that dense connection means that every neuron is connected to every other neuron.

- 29

- 198

Ans: B. *Number of interconnections  =  number of neurons in layer 'l' x number of neurons in layer 'l-1'*

#### Assumptions of Neural Network

Qn: According to the assumptions of Neural Network, the activation function of all the neurons in a particular layer is the same. True or False.

- True

- False

Ans: A. *It is one of the simplifying assumptions.*

In the upcoming session, you will learn about the first step of the model building process in deep learning.