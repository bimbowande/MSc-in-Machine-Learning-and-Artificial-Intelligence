# Sequential vs Functional API

As seen earlier, there are three kinds of the model building process. Among them, the most used and common is the Sequential and Functional API. They both are user friendly and allows us to work on simple and traditional use-cases.

In the next video, let's quickly revise the Sequential API approach which you have used in the earlier modules.

**VIDEO**

**Sequential API:** Here layers are put in sequential order and the flow of data takes place between layers in one direction. It is the most common type of model to create simple neural network architectures where we have a linear stack of layers.

This is the best approach for a beginner as it is user-friendly and you can create models by simply plugging together building blocks. The only disadvantage of using the Sequential API is that it doesn’t allow us to build Keras models with multiple inputs or outputs. Instead, it is limited to just 1 input tensor and 1 output tensor. 

Using a sequential() function, you can build your model by passing a list of layers. 

```python
model =  keras.Sequential( [
					layers.Dense(16, activation="relu", name="layer1"),
			        layers.Dense(8, activation="relu", name="layer2"), 
                    layers.Dense(4, name="layer3") ] )
```

Sequential models can also be created incrementally using the `add()` method.

```python
model = keras.Sequential()
model.add(layers.Dense(16, activation="relu", 
```

You may have already worked with some of the models that utilise Sequential approaches like VGGNet, LeNet and AlexNet.

So, now that you have understood how we implement the Sequential function for our simple models, let's understand the next model building processes, i.e. through the use of functional APIs.

**VIDEO**

**Functional API:** This type of approach allows you to build neural network models with **multiple inputs/outputs that also possess shared layers**. It can do all the work which you could do with the sequential API and on top of it provides more control over how the layers should interact with each other.

Here layers are appended to each other by passing input to them. As seen in the video, **x** acted as the input variable to subsequent layers. So compared to the previous approach, here you have a decent degree of customisation which you can add to your model.

Functional API uses the concept of legos which once you have built, can be fit anywhere to shape your final model. A model might have many blocks in it to perform different operations on the built-in layers.  Imagine these blocks as **legos** that can be shaped/stacked in any manner to define the architecture of your model.

![Each module inside the models is a lego block. You can stack/shape them in any particular way to build the final model.](https://i.ibb.co/jyGBS9x/Legos.png)

Each module inside the models is a lego block. You can stack/shape them in any particular way to build the final model.

Once these blocks are built, they can be used any number of times, thus providing us with the benefit of reusability. Let's take an interesting example to understand how we can build blocks and reuse them for defining our model architecture.

Imagine you want to create a **CNN block** that applies both the convolutional operation and BatchNormalisation. You also want to apply a ReLU activation function to the output of both the above operations. 

![CNN Block](https://i.ibb.co/chnfKPF/CNN-Block.png)

Here is the code for implementing the block above.

```python
def CNN_block(x,filters, kernel_size=3, padding="same"):
    # Defining a function which returns an operation of Convolution, BatchNormalisation and Relu.
    # Here x is the input.
    x = Conv2D(filters, kernel_size=3, padding)(x)
    x = BatchNormalization()(x)
	
    return tf.nn.relu(x)
```

Now, let's say you want to create an **inception block** that utilises the earlier created CNN block multiple times and produces the output by merging the results from the CNN blocks.

![Inception Blocks](https://i.ibb.co/0mQ4cwt/Inception-Blocks.png)

Here is the code for implementing the block above.

```python
def inception_block(x, filter1, filter2):
	# Defining a function which applies two CNN blocks. The output of both these blocks are then concatenated
	conv1 = CNN_block(x, filter1)
	conv2 = CNN_block(x, filter2)
	x = keras.layers.concatenate([conv1, conv2])

	return x
```

Here, the **inception_block** uses two branches of the **CNN_block.** The outputs coming from these two branches are then merged together by passing two instances of CNN_block as a list to the [**layers.concatenate**](https://keras.io/api/layers/merging_layers/concatenate/) layer.

This feature is called **Shared layers**, where you have **reused the same block again inside our new block/lego.** By sharing the information across two or more different inputs, shared layers allow you to train a model even on lesser data.

Now that you have defined all the blocks that would be used for the model, you can go ahead and build the architecture for the same. Consider the model that you want to build is the following.

```
(input shape: 28,28,1))
		↓
[CNN_block(32 units)]
		↓
[MaxPooling2D(3)]
		↓
[Inception_block (32 units, 32 units)]
		↓
[Inception_block (64 units, 64 units)]
		↓
[CNN_block(128 units)]
		↓
[GlobalAveragePooling2D()] 
		↓ 
[Dense (256 units, relu activation)] 
		↓ 
[Dropout(0.5)] 
		↓ 
[Dense (10 units)] 
		↓ 
(output: logits of a probability distribution over 10 classes
```

Here is the code for implementing the architecture above.

```python
inputs = keras.Input(shape=(28, 28, 1))
x = CNN_block(inputs,32)
x = layers.MaxPooling2D(3)(x)
x = inception_block(x,32, 32)
x = inception_block(x,64, 64)
x = CNN_block(x,128)
x = layers.GlobalAveragePooling2D()(x)
x = layers.Dense(256, activation="relu")(x)
x = layers.Dropout(0.5)(x)
outputs = layers.Dense(10)(x)
model = keras.Model(inputs, outputs, name="final_model")
model.summary()
```

The summary of the model is as follows.

```python
Model: "final_model"
__________________________________________________________________________________________________
Layer (type)                    Output Shape         Param #     Connected to                     
==================================================================================================
input_1 (InputLayer)            [(None, 28, 28, 1)]  0                                            
__________________________________________________________________________________________________
conv2d (Conv2D)                 (None, 28, 28, 32)   320         input_1[0][0]                    
__________________________________________________________________________________________________
batch_normalization (BatchNorma (None, 28, 28, 32)   128         conv2d[0][0]                     
__________________________________________________________________________________________________
tf.nn.relu (TFOpLambda)         (None, 28, 28, 32)   0           batch_normalization[0][0]        
__________________________________________________________________________________________________
max_pooling2d (MaxPooling2D)    (None, 9, 9, 32)     0           tf.nn.relu[0][0]                 
__________________________________________________________________________________________________
conv2d_1 (Conv2D)               (None, 9, 9, 32)     9248        max_pooling2d[0][0]              
__________________________________________________________________________________________________
conv2d_2 (Conv2D)               (None, 9, 9, 32)     9248        max_pooling2d[0][0]              
__________________________________________________________________________________________________
batch_normalization_1 (BatchNor (None, 9, 9, 32)     128         conv2d_1[0][0]                   
__________________________________________________________________________________________________
batch_normalization_2 (BatchNor (None, 9, 9, 32)     128         conv2d_2[0][0]                   
__________________________________________________________________________________________________
tf.nn.relu_1 (TFOpLambda)       (None, 9, 9, 32)     0           batch_normalization_1[0][0]      
__________________________________________________________________________________________________
tf.nn.relu_2 (TFOpLambda)       (None, 9, 9, 32)     0           batch_normalization_2[0][0]      
__________________________________________________________________________________________________
concatenate (Concatenate)       (None, 9, 9, 64)     0           tf.nn.relu_1[0][0]               
                                                                 tf.nn.relu_2[0][0]               
__________________________________________________________________________________________________
conv2d_3 (Conv2D)               (None, 9, 9, 64)     36928       concatenate[0][0]                
__________________________________________________________________________________________________
conv2d_4 (Conv2D)               (None, 9, 9, 64)     36928       concatenate[0][0]                
__________________________________________________________________________________________________
batch_normalization_3 (BatchNor (None, 9, 9, 64)     256         conv2d_3[0][0]                   
__________________________________________________________________________________________________
batch_normalization_4 (BatchNor (None, 9, 9, 64)     256         conv2d_4[0][0]                   
__________________________________________________________________________________________________
tf.nn.relu_3 (TFOpLambda)       (None, 9, 9, 64)     0           batch_normalization_3[0][0]      
__________________________________________________________________________________________________
tf.nn.relu_4 (TFOpLambda)       (None, 9, 9, 64)     0           batch_normalization_4[0][0]      
__________________________________________________________________________________________________
concatenate_1 (Concatenate)     (None, 9, 9, 128)    0           tf.nn.relu_3[0][0]               
                                                                 tf.nn.relu_4[0][0]               
__________________________________________________________________________________________________
conv2d_5 (Conv2D)               (None, 9, 9, 128)    147584      concatenate_1[0][0]              
__________________________________________________________________________________________________
batch_normalization_5 (BatchNor (None, 9, 9, 128)    512         conv2d_5[0][0]                   
__________________________________________________________________________________________________
tf.nn.relu_5 (TFOpLambda)       (None, 9, 9, 128)    0           batch_normalization_5[0][0]      
__________________________________________________________________________________________________
global_average_pooling2d (Globa (None, 128)          0           tf.nn.relu_5[0][0]               
__________________________________________________________________________________________________
dense (Dense)                   (None, 256)          33024       global_average_pooling2d[0][0]   
__________________________________________________________________________________________________
dropout (Dropout)               (None, 256)          0           dense[0][0]                      
__________________________________________________________________________________________________
dense_1 (Dense)                 (None, 10)           2570        dropout[0][0]                    
==================================================================================================
Total params: 277,258
Trainable params: 276,554
Non-trainable params: 704
```

You can also plot the model as a graph using the following command.

```python
keras.utils.plot_model(model, "final_model.png", show_shapes=True)
```

![Final Model](https://i.ibb.co/DwPFQBL/final-model.png)

To learn more about Functional API, read the [guide.](https://keras.io/guides/functional_api/)

## Coming Up

In the next segment, you will learn about the third approach - Model Subclassing.