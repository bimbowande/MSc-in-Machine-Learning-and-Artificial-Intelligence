# Graded Questions

#### More layers

Suppose you make two CNN architectures, one with 15 layers (A) and another with 35 layers (B), and train them both (with identical infrastructure, training scheme etc.) on a 10-class classification task. The performance of the models is as follows:

-   Model-A: Training accuracy = 85%, validation accuracy = 82%
-   Model-B: Training accuracy = 78%, validation accuracy = 73%

Which of the following could be a possible explanation for these results?

- Model-B, being huge, is overfitting and is thus not performing well

- Model-B, being huge, is difficult to train (could because of infrastructural constraints or issues such as vanishing/exploding gradient)

- Model-B is underfitting, perhaps because larger networks sometimes have low 'learning capacity'

Ans: B. *This is the most likely explanation - larger networks are harder to train. The reason could be either of the two mentioned above.*

#### Transfer Learning

Qn: In which of the following cases can we use transfer learning? More than one options may be correct.

- We have a massive dataset in one domain and a smaller dataset in other similar domain.

- We have a pre-trained model in one domain and a massive dataset in other similar domain.

- We have a pre-trained model in one domain and a smaller dataset in another similar domain.

Ans: All of the above. *We should definitely use transfer learning if we do not have enough training data. We can use the pre-trained model and retrain it a little for our own purpose. Since we also have a massive dataset, the model should achieve good accuracy as well.*

#### Learning rate in Transfer Learning

Qn: Suppose we are using the pre-trained weights from a large model and re-training our own model in a transfer learning setting. What should be the learning rate of the pre-trained weights? Assume that we can use a different learning rate for each layer. More than one options may be correct.

- As we move from the last layer to the initial layers, we should decrease the learning rate because the initial layers are good at extracting generic features while the last few layers are usually trained for a specific task 

- As we move from the last layer to the initial layers, we should increase the learning rate because the initial layers need to 'unlearn' more of what they had learnt from the original task, while the layers deeper in the network are well-suited to directly transfer their knowledge to the new task

- We can have any learning rate, doesn’t matter, after all, we are training a new model.

Ans: A.

#### Analysis of Deep Neural Networks

Qn: Which of the following statements are correct? More than one options may be correct.

- The number of operations in a network is directly proportional to the inference time (i.e. the time taken for a feed-forward).

- The number of parameters in a network is directly proportional to the inference time (i.e. the time taken for a feed-forward).

Ans: A. *The computational time is proportional to the number of operations required.*

#### Analysis of Deep Neural Networks

Which of the following network is the most suited for a real-time face recognition task in a mobile app?

![Analysis of Deep Neural Networks](https://i.ibb.co/ZJjzWWZ/Analysis-of-Deep-Neural-Networks.png)

- ENet

- VGGNet

- AlexNet

- ResNet-152

Ans: A. *ENet has much lesser parameters (small bubble size) than the others, so it requires much less memory. Also, the inference time is the lowest (proportional to the number of operations), which is important for a real-time task. It also has decent accuracy.*
