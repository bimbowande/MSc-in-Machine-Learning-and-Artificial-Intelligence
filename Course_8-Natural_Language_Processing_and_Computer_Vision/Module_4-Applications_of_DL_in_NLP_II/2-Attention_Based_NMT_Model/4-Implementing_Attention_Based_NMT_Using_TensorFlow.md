# Implementing Attention-Based NMT Using TensorFlow

You have come a long way. You have learnt what attention modelling is and how it is integrated with the encoder-decoder architecture. Let’s now implement the same and improve the model created in the earlier demonstration.

**VIDEO**

In this demonstration, the goal remains the same as we have seen in the earlier traditional NMT model i.e. to convert a sentence from the source language (English) to the target language (Hindi).

The notebook mentioned in the video can be downloaded from [here](https://drive.google.com/file/d/1_akBiYHzPAZ-Rynkzakr-0xxAc0s4pE-/view?usp=sharing)

For most of the attention-based NMT models, the process remains the same as earlier since we are working on the same data set. In the next video, Mohit will take you through the entire implementation and will help you understand the changes that are introduced to make the model prediction better and solve the information bottleneck problem.

**VIDEO**

## Model building

The following image shows us the entire architecture of the attention-based NMT model you are going to build.

![Attention Architecture](https://i.ibb.co/G9b47N5/Attention-Architecture.png)

As seen in the video the Encoder remains the same, however, the encoder output is not discarded here and is used as an input to the attention model. 

## Attention model

To the decoder, the **encoder_output** is added as an added input to generate the context vector. The encoder_output and decoder's hidden state is passed as input to the **Bahdanau's attention model** (Additive attention). 

Here is the code for the attention model:

![Attention code](https://i.ibb.co/cvRLDQ9/Attention-Code.png)

Once you have built your attention model successfully you can observe: 

Attention result shape (context vector): **(batch size, units) =**  (64, 1024)

Attention weights shape: **(batch_size, sequence_length, 1) =** (64, 72, 1)

Once the context vector is generated, it is then concatenated with the output from the embedding layer. This concatenated result is fed to the GRU layer as input. The other components of the Decoder remain the same.

In the end, you have seen how beam search improves the model performance and how it performs a better job even when it is fed with longer sentences. To understand more on the beam search refer the `beam_search_step` the function used in the demonstration.

You are now ready to experiment with NMT and attention models and how they can be tuned to increase the model’s performance. All the best!