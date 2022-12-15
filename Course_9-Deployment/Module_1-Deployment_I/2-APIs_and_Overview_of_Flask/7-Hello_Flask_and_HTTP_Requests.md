# Hello Flask & HTTP Requests

In the previous segments, you learned about Flask and its various features. You also installed Visual Studio on your machine.

In the next video, you will develop a basic “Hello Flask” application after installing Flask on your system.

The following folder contains all the required files that will be used in the next video. Refer to this folder before proceeding to the video.  
 

Download Hello Flask File

You can directly import the entire folder into Visual Studio using the drop-down options shown below.

![Import the entire folder into Visual Studio using the drop-down options](https://i.ibb.co/SfkLwCR/Visual-Studio-Drop-Down-Options.png)

Let's do the hands-on using Visual Studio in the next video.

**VIDEO**

Run the following command on the command prompt to install Flask on your system:

`pip install flask`

If you have already installed Anaconda, then you can use the following command to install Flask:

`conda install flask`

After installing Flask, you need to run the “Hello Flask” application using the file that was provided at the beginning of this segment.

Let’s try to understand the code line by line.  
 
```python
from flask import Flask

app = Flask(__name__)
```

These lines of code import the Flask library. Once you import Flask, you must create an instance of the Flask class for your web application. That is what “app = Flask(__name__)” does. 
  
“`__name__`” is a special variable that gets as value the string “__main__” when you execute the script.

```python
@app.route("/") 
def home(): 
	return "Hello World"
```

Using route(), Flask orders the web application to route the request to the home() function if the browser requests the address / (the default, or home address). In other words, route() helps you define the “path” for the various functions in the web application.
  
The home() function returns the string “Hello World”. This will be sent to the web browser.

You are now defining a function that returns the string “Hello World”. This function is mapped to the home "/" URL. This means that whenever a user navigates to localhost:5000, the home function will run and return its output on the web page.

```python
@app.route("/submit") 
def submit(): 
	return "Hello from submit page"
```

If the input to the route method is different, for example,  “/submit”, then the submit() function will be shown whenever a user visits localhost:5000/submit.

`if __name__ == '__main__': app.run()`

Here, Python assigns the name “`__main__`” to the script when the script is executed. If the script is imported from another script, then the name of the script will remain the same as that of the original script. Suppose the name of the imported script is “hello.py”, then the name of the script will remain the same. 

In your case, you are executing the script; therefore, “`__name__`” will be equal to “`__main__`”. This means that if the conditional statement is satisfied, then the `app.run()` method will be executed. This technique allows the programmer to control the script's behavior.

#### Flask Port

Qn: What is the default port of Flask?

- 6000

- 5000

- 4040

- 8888

Ans: B. *The default port of Flask is 5000.*

#### Flask

Qn: What will the URL be to print “Hello-Universe” when you run the following lines of code?

```python
from flask import Flask 

app = Flask(__name__) 

@app.route("/")
def home():
	return "Hello-World" 

@app.route("/sub")
def submit():
	return "Hello-Universe" 
	
if __name__ == '__main__':
	app.run()
```

- `http://127.0.0.1:5000//sub`

- `http://127.0.0.1:5000/`

- `http://127.0.0.1:5000/sub `

- `http://127.0.0.0:8888/sub`

Ans: C. 

In the next video, you will learn about HTTP.

**VIDEO**

HTTP stands for hypertext transfer protocol. A web application depends on various protocols through which you interact with all the resources that are available on websites. One of the popular protocols is HTTP.

The HTTP API approaches are as follows:

-   Representational state transfer (REST)
-   Remote procedure call (RPC)

These approaches have the following in common:

1.  **Resources**: A resource is the key abstraction of information in REST. Any information can be a resource, such as a document, an image, a temporal service, and a collection of other resources, which is displayed on a website.   
    This can be interpreted as the HTML files that are located on the server and are being accessed by clients. 
2.  **Verbs**: In the segment on REST, you were introduced to the four URL methods: GET, POST, PUT, and DELETE. These methods are also called verbs, which can be used to access any resources that you want. They are as follows:

-   GET: It is used to request data/resources from a specified server.
-   POST: It is used to send data to a server to create/update a resource.
-   PUT: It is used to send data to a server to replace / fully update a resource.
-   DELETE: It deletes the specified resource.

In the next segment, you will learn about the HTTP requests (verbs) in detail.