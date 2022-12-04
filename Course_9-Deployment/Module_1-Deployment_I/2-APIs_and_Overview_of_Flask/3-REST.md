# REST

REST is an acronym for **representational state transfer**. It refers to the set of rules that are followed while creating APIs to ease communication. 

Let’s hear from Abhay as he explains what REST is.

**VIDEO**

A system is known as **RESTFUL** if it follows all the given constraints. As per these rules or constraints, we should be able to get data when we link to a certain URL.

  
A uniform resource locator (URL) consists of the following parts:

Endpoint

Methods

Headers

Data (Body)

-   **Endpoint:** This is the URL that you see in the address bar. Suppose you have a URL _http"//github.com._ Then, this particular URL is called the “endpoint”. Also, if you look into this URL, this is the base URL of the GitHub website. Therefore, it is called the “root endpoint”.

-   **Path:** Suppose you have accessed a website, say, _http://github.com._ Now, suppose you want to get resources from a particular part of this website, and the URL for that is _http://github.com/tensorflow/tensorflow._ Then, _'tensorflow/tensorflow'_ will be the path, and _'http"//github.com'_ will be the root endpoint. The path identifies the specific resource within the host that the user wants to access.

For any URL, you will have the following structure to get information from the web page.

**"Root endpoint + Path"**

-   **Method:** The resource methods used to perform a desired transition are one of the most important aspects associated with REST. Each URL has a set of methods associated with it, such as GET, POST, PUT, and DELETE. You will get a clearer idea of this as we proceed in this module. 
-   **Headers**: These are some of the elements that are passed along with the URL, such as an API token to verify a particular user. The HTTP headers are used to pass additional information between the clients and the server through the request and response header.  HTTP header fields provide the required information about the request or response or about the object sent in the message body. You can refer to [this](https://www.soapui.org/learn/api/understanding-rest-headers-and-parameters/) link to know more about HTTP headers.
-   **Data (Body)**: Details such as username and password during login are passed as data in the URL. If you rate a movie on IMDb, the rating is passed as a data point in the body. You will get a better understanding of this when you create an HTML page in the coming segments, wherein you will learn how the POST method is used to add the body.  
     

Suppose you want to create a web page from the Iris data set to predict the Iris type, as shown below.

![Iris Data Prediction](https://i.ibb.co/dJGLTyd/Iris-Data-Prediction.png)

Let's take the example of the HTML page given below and see what the body of an HTML page looks like.

```html
<body>  <div class="login">    <h1>Iris Data Prediction</h1>    <!-- Main Input For Receiving Query to our ML for the fields,  area, bedroom, bathrooms, 'basement', stories, guestroom, parking, areaperbedroom, bbratio-->    <form action="{{ url_for('predict')}}" method="post">      <input type="text" name="sepal_length" placeholder="sepal length" required="required" /><br><br>      <input type="text" name="sepal_width" placeholder="sepal width" required="required" /><br><br>      <input type="text" name="petal_length" placeholder="petal length" required="required" /><br><br>      <input type="text" name="petal_width" placeholder="petal width" required="required" /><br><br>            <button type="submit" class="btn btn-primary btn-block btn-large">Predict</button>    </form>    <br>    <br>    {{ prediction_text }}  </div> </body>
```

Here, you have included four inputs: sepal length, sepal width, petal length, and petal width, along with the 'Predict' button, in the body of the HTML page. The inputs are POSTed to the server as you click on 'Predict'. Similarly, if there was another button 'Show' that showed a flower with a particular index, you would send a GET request to the server.

In the next video, you will learn the difference between a client and resources.

**VIDEO**

Two terms are associated with the REST API:

1.  **Client**: This is the application platform where you request resources. For example, when you use the Twitter API to search for tweets on the application, the application is your client.
2.  **Resource**: The key abstraction of information in REST is a resource. Any information that can be named can be a resource; it could be a document or image, a temporal service, a collection of other resources, and so on. The concept of a REST resource is abstract. It is basically "whatever thing is accessed by the URL you supply". It can be the data that you send or receive via a URL. The URL is not a resource; it is a label that identifies the resource. It can be thought of as the name of the resource.

As you learned above, some **resource methods** (GET, POST, PUT, and DELETE) are associated with REST, which is used to perform the desired transition.

You can refer to the following link to learn more about REST:  
[REST Readings](https://restfulapi.net/)

#### REST

Qn: What is REST?

- Representational state transfer

- Representational service transfer

- Real state transfer

- Representational server transfer

Ans: A.

Qn: Find the root endpoint for the URL below. URL: `https://github.com/username/git-repo`

- `https://github.com`

- `https://github.com/username`

- `https://github.com/username/git-repo`

- `/username/git-repo`

Ans: A. *The root endpoint is the base website URL that you want to access.*

Qn: Find the path for the URL below. URL: `https://github.com/username/git-repo`

- `https://github.com`

- `https://github.com/username`

- `https://github.com/username/git-repo`

- `/username/git-repo`

Ans: D.
