# HTTP Requests Demonstration

In the previous segment, you learned how to run a basic “Hello_Flask” web application using Visual Studio and Python's Flask library. 

Websites are designed using HTML, CSS, and JavaScript. In the next video, you will learn how to create an HTML file.

**VIDEO**

In this video, you learned that you can build a simple HTML page using the following code:

```html
<head> <title> Home Page</title> <head>
```

In the lines of code provided above, you have defined the head of the web page with the title **Home Page.**

```html
<body> <h1> Home Page Header</h1> <p> Hello from Home Page</p> <body>
```

Here, the header `<h1>` is defined as “Home Page Header”, and the paragraph `<p>` is defined as “Hello from Home Page”, which will be printed on the home page. 

```html
<from action= “#” method= ‘post’>        <p>Form fields:</p> <p><input type= “areaofhouse” name= “AreaOfHouse” </p> <p><input type= “submit” value= “submit” </p> </from>
```

In this segment of code, you have defined the three paragraphs:

-   “Form fields” is going to print on the web page.
-   “AreaOfHouse” is defined as an input field to get users’ inputs.
-   “submit” is defined as the button to submit the value of AreaOfHouse.

The structure of this HTML page will look as shown below.

![Structure Sample HTML Page](https://i.ibb.co/vk03Xhw/Structure-Sample-HTML-Page.png)

You already know that Flask is used to create a web application and that it works as a bridge between the back end and the front end. In this example, we have already developed the front end using HTML. Now, the next step is to create a web application using Flask.

Now, you need to import Flask and render_template. Then, you need to add the following lines of code in the “app.py” file:

```python
@app.route("/")
def home():
	return render_template(“index.html”)
```

Now, the home page will be rendered using the Flask application on the local. In the next video, you will learn about the two HTTP requests, GET and POST.

**VIDEO**

#### HTTP Requests

Qn: If you put the `http://127.0.0.1:5000`? Then what will be the method that will be fired up?  

- GET

- POST

In the previous segment, you learned the meaning of HTTP requests. Now, we will help you understand HTTP requests in a more practical way.

You already know that verbs are used to access resources. Some of the important HTTP requests have been described below:

-   **GET**: This method is used to retrieve information from a given server.
-   **POST**: This method is used to send data to a server to create/update a resource. It is also used to send information to a server. Examples of this include filling out an online form (i.e., sending a large amount of complex data to the web server) and commenting or changing one's profile picture on a forum. The POST method is used to send user-generated data to the web server. Using this method, one can send a large amount of data, as data is sent in body. Here, data is not exposed in the URL; hence, it is a secure way to send data.
-   **PUT**:  This method is used to send data to a server to replace / fully update a resource. It is also used to send a replacement document or upload a new document to a web server under the request URL. This method completely replaces everything that currently exists at a target URL with something else.
-   **DELETE**: This method deletes a specified resource.

Let's get an intuitive understanding of HTTP methods.

Suppose you have an IMDb web page. When you log into this page using your Gmail/mail/Facebook account, it enables you to rate any movie.  Suppose you give a particular movie a rating of “8”. It will POST this rating of “8” to the server. If you want to see the overall average rating of a particular movie on the IMDb page, it processes a GET request to get the required information. If you want to delete your rating from the web page, it processes the DELETE request to delete the rating given by you.

Please refer to the following links to understand HTTP requests in detail.

  
[HTTP Requests-I](https://www.keycdn.com/support/put-vs-post)  
[HTTP Requests-II](https://techdifferences.com/difference-between-get-and-post-method-in-html.html)

  
Let’s discuss the GET and POST methods one by one.

```python
@app.route("/", method=[‘POST’, ‘GET’])
def home(): 
	if request.method == ‘POST’:
		return render_template(“index.html”, placeholder_text=”Hello from Post method”)
	if request.method == ‘GET’: 
		return render_template(“index.html”, placeholder_text=”Hello from Get method”)
```

When you run the method given above and get the URL, it will print the “Hello from Get method” because the request.method will be executed using the GET condition. But if you put any value in the input box on the web page, then it will call the “index.html” file, and using the POST method, it will enter into the ‘POST’ condition of the “if” statement and print the output as “Hello from Post method”.

#### HTTP Requests

Qn: Which of the following statements are true about the GET and POST methods?

- GET is used to request data from a specified resource.

- The query string is sent in the URL of a GET request.

- POST is used to send data to a server to create/update a resource.

- GET is better for data that is secure.  
 
Ans: A, B & C. *The GET method is meant to request data from a specified resource. In the case of GET requests, only a limited amount of data can be sent because data is sent in the header. A POST request is used to send data to a server to create/update a resource. In a POST request, a large amount of data can be sent because data is sent in the body.*