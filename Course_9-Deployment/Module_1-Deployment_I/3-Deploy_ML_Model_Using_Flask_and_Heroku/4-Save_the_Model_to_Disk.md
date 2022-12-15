# Save the Model to Disk

In the previous segment, you learned how to build a linear regression model in Visual Studio. Also, you performed certain relevant preprocessing steps, after which you verified the model using an input array of nine features.

In the forthcoming video, you will learn how to encapsulate the ML model using “pickle.”

**VIDEO**

As a data scientist, you will be using different types of data in the form of dictionaries, DataFrames or in other data types. When working with these data types, you may want to save them to a file so that you can use them later or send them to someone. This is what Python’s pickle module is for.

It serializes objects (saves them to disk) so that they can be saved to a file and loaded in a program again later.

Pickle is used for serializing and deserializing Python objects. Serialization can be referred to as the process of converting an object in memory to a byte stream that can be stored on disk or sent over a network. This character stream can be retrieved later and deserialized back into a Python object. Note that pickling is not the same as compression.

Pickle is not recommended if you want to use data across different programming languages as its protocol is specific to Python. Thus, cross-language compatibility is not guaranteed in pickle.

When you run code, you will see that it creates a new file named model.pkl, which can be used by the Flask application to orchestrate it with the ML model.

In the next segment, you will learn how to build front-end HTML codes to have a user-friendly interface to interact with the ML model and obtain predictions.

#### Serialization and Deserialization

Qn: Which of these statements is true?  
 
- This process of saving an ML model is also known as object deserialization.

- The restoring/reloading of ML Model procedure is known as serialization. 

- The pickle library can only perform serialization tasks. 

- The pickle library can perform both serialization and deserialization tasks. 

Ans: D. *`pickle.dump()` performs serialization tasks, while `pickle.loads()` performs deserialization tasks.*
