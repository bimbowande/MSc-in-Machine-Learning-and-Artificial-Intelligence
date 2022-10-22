# Experiments with RNN Architecture - Part II

You have already seen that RNN architecture can be modified as per the suitability of the problem in hand. You also saw that you can add non-RNN layers like a classification layer on the top of RNN layers to do a classification task. Next,  you learnt how to input multiple sequences into RNN. Now, what if you need multiple output sequences from the RNN unit?

Let’s learn in the next video.

**VIDEO**

Now, you know that you will need multiple RNN units for producing multiple outputs as each RNN unit can produce only one output. This in turn will increase the number of parameters in our model.

#### Feed Forward Expression for Multiple Inputs

Qn: According to the convention followed by Prof. for the input sequences and weights, which of the following is the right formula to get the new hidden state ht from the old one ht-1 in the case of three input sequences a, b and c and one hidden unit?

- $f_w(W_{Fa}∗x_{tb}+W_{Fb}∗x_{tc}+W_{Fa}∗x_{tc}+W_F∗h_t)$

- $f_w(W_{Fb}∗x_{ta}+W_{Fa}∗x_{tb}+W_{Fc}∗x_{tc}+W_R∗h_{t-1})$

- $f_w(W_{Fb}∗x_{tb}+W_{Fa}∗x_{ta}+W_{Fc}∗x_{tc}+W_R∗h_{t-1})$

- $f_w(W_{Rb}∗x_{ta}+W_{Ra}∗x_{tb}+W_{Fc}∗x_{tc}+W_R∗h_{t-1})$

Ans: C. *The overall input will be the current input at time $t$ $x_{ta}$, $x_{tb}$ and $x_{tc}$ and all of them will have their own weights $W_{Fa}$ , $W_{Fb}$ and $W_{Fc}$ respectively. On the other hand, old hidden state $h_{t−1}$ will get multiplied with recurrent weights $W_R$.*

In the next section, you will learn about the parameters involved in the RNN architecture.