# Architecture of RNN - I

In the previous segments, you looked at different examples of sequential data and the fact that RNNs help in modelling sequential data but how does RNN do that? In this segment, you will have a look at a deeper picture to understand the functioning of RNN from an architectural perspective.

Let’s first start with understanding the rolled representation of RNN.

**VIDEO**

So, you saw how the output is being calculated and how the hidden state gets updated across time steps. Also, all the weights and biases are shared for each time step. Let’s understand this using an example.

In the diagram given below, the input ($\large{x_t}$) and hidden state ($\large{h_t}$) are shown at each time step $\large{t}$, which are changing across time steps. Note that the following is an unrolled version of RNN.

![Unrolled Version of RNN](https://i.ibb.co/Kqrg8GT/Unrolled-Version-of-RNN.png)

Both $\large{x_t}$ and $\large{h_t}$ have their separate weights $W_F$ and $W_R$ respectively, which remain the same for each time step as depicted by just using $W_F$ and $W_R$ at each time step. You can understand the shared weights with a rolled RNN diagram given below, where we are just showing one weight $W_F$ for feed-forward connections and $W_R$ for recurrent connections.

![Rolled RNN](https://i.ibb.co/0rVHwt0/Rolled-RNN.png)

Also, in all of the RNN architectures that you have seen, hidden state $\large{h_t}$ is being treated as final output hence $\large{y_t}$ is the same as $\large{h_t}$ here. You’ll learn in the later segments that you can apply another activation layer on the $\large{h_t}$ which causes $\large{y_t}$ to be different from $\large{h_t}$.

Now, let’s see how the RNN elements such as input, output and hidden state work in tandem with an example.

**VIDEO**

Did you notice that when the part-of-speech tag was assigned to the word ‘book’, the model must have an understanding of the positioning of the word since ‘book’ can be a noun (I have a book) as well as verb (I booked two movie tickets)?

#### Hidden State in RNN

Qn: While making predictions in RNN, we input the previous hidden state of time step $t-1$ $(h_t-1$)$ in the RNN cell to get access to the information of \_\_\_\_\_?

- Past input at $t-1$

- All the past inputs prior to time step $t-1$

- All the past inputs upto time step $t-1$

- All the past inputs till time $t$

Ans: C. *Since the old hidden state $(h_t-1)$ gets influenced by all of the prior inputs till time step $t-1$ hence it provides information of all the past inputs upto time $t-1$.*

In the next segment, you will learn RNN architecture in more detail.