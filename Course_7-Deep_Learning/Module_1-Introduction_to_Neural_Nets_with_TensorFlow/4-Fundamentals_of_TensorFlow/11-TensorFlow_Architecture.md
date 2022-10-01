# TensorFlow Architecture

In this segment, we will dive deeper into the architecture of TensorFlow. Although the learning from this segment will not affect your learning in the upcoming segments, it is always helpful to understand how TensorFlow executes code in the background. In the forthcoming video, Avishek will explain the basic architecture of TensorFlow.

**VIDEO**

The core of TensorFlow is the C++ engine, which is responsible for communicating with the other engines, such as the distributed master (explained later in this segment), kernel implementations and the actual devices on which the computations will be run.

  
Additionally, on top of the C++ core is built a Python API, which provides developers with a high-level language for passing instructions to the core. Using the Python API, high-level modules, such as tf.math and tf.linalg, are built. These modules provide basic functionalities out of the box and save a lot of effort, which might have otherwise been wasted in writing boilerplate low-level code. All the functions that you explored in this session belong to this layer. Libraries that make ML tasks easier are built on top of modules such as tf.math and tf.linalg. Keras is one such library, and the next session will introduce you to this library. 

  
**Distributed Architecture**   
Throughout this session, all the demonstrations have been performed on a single device provided by the Google Colab platform. But regardless of the size of the machine provided, you are bound to encounter data so big that a single machine will not be able to process it. So, it becomes important to be able to distribute tasks across multiple machines or devices. TensorFlow is also capable of distributing the learning process. In the forthcoming video, you will learn how TensorFlow executes distributed learning. 

**VIDEO**

Distributed computation in TensorFlow can be divided into these three main steps: Client, distributed master and workers. Let us discuss each of them now:

1.  **Client:** The job of the client is to build a computational graph using the available APIs. Earlier in this segment, you learnt that the heart of TensorFlow is the C++ core and different APIs are built on top of it. The objective of the client is to make sure all the tensors and the operations to be carried out on the tensors are communicated to the TensorFlow core.   
     
2.  **Distributed master:** It receives the complete computational graph from the client-side. The distributed master first runs some rule-based optimisations, for example, combining constant nodes, if present. Then the master creates subgraphs from the computational graph so that the workers can work individually in the subgraphs.  
     
3.  **Workers:** There are two types of worker processes: One is a parameter server and the other is the actual computation work. The parameter server, as the name suggests, is responsible for holding all the necessary parameters and data. Its sole job is to keep all the parameters updated for other workers to use and update. 

The second type of job that the workers do is the actual computation. All the workers access data from the parameter server and perform the operations that are defined in the subgraph given to each of them. And after the computations are complete, they update the parameter server so that the remainder of the process can be carried out.

  
The data flows from the client to the master and then to the workers. The workers communicate between themselves and complete their job, and after the required computation is complete, the data is sent back to the client for the user to access.

  
With this, you have covered all the fundamentals of TensorFlow as an ML library. Keep in mind that TensorFlow is not only an ML library but also an end-to-end ML solution platform. It has numerous types of modules and capabilities, which help with many different types of tasks in the life cycle of a solution. In the next video, our SME will discuss some of the other modules in TensorFlow that were not within the scope of this module.

**VIDEO**

Hopefully, you now appreciate the completeness of TensorFlow as an end-to-end ML solution builder platform. In the upcoming segments, you will be building a neural network to classify handwritten digits using TensorFlow libraries.