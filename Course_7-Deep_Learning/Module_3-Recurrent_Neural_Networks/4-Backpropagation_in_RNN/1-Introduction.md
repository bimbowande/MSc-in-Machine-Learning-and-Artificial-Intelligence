# Introduction

In session 1, you got to know an overview of RNN, its architecture and its training process. You also got an overview of backpropagation in RNN which is also named Backpropagation Through Time (BPTT). We discussed the final error gradient of recurrent weights $W_R$ but we left out the derivation.

However, if you wish to learn more, in this session, we will cover derivations of the error gradients with respect to all the weights involved. This session contains the advanced study material related to the backpropagation in RNN.

**In this session:**

-   Calculation of error gradients against feed-forward weights, $W_F$
-   Calculation of error gradients against output weights, $W_O$
-   Calculation of error gradients against recurrent weights, $W_R$
-   Mathematics behind the vanishing and exploding gradient problem in RNNs

## You’ll be hearing from

**Mouli Sankaran**

**Visiting Professor, CS Department, IIIT Lucknow**  
Professor Mouli is currently working as a visiting faculty at IIIT Lucknow, handling courses on AI for IoT and Python. He has a total of 30+ years of experience in networking, embedded software, machine learning with 24+ years industrial experience in defining, designing, and delivering high-quality products & systems and 6+ years in teaching. He has made his name in both academics as well as industry and that has always ensured that he is above the bar whenever he delivers the content.