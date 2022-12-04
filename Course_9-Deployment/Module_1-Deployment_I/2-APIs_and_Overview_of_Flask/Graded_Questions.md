# Graded Questions

Now that you have gone through the entire session, please attempt the following graded questions.

#### REST

Qn: In any request, the data (or body/message) contains information that must be sent to the server.  Which of the following requests cannot be used with data?

- GET

- POST

- PUT

- DELETE

Ans: A. *The HTTP GET request should only receive data. If you want to change_ data _on the server, use the POST, PUT, or DELETE methods.*

#### Flask

Qn: What is the extension of the Flask application?

- .html

- .py

- .pkl

- .ipynb

Ans: B.

#### HTTP Requests

Match the following.

|           |                                                                              |
| --------- | ---------------------------------------------------------------------------- |
| a. GET    | 1. It deletes a specified resource.                                          |
| b. POST   | 2. It is used to request data from a specified resource.                     |
| c. PUT    | 3. It is used to send data to a server to replace / fully update a resource. |
| d. DELETE | 4. It is used to send data to a server to create/update a resource.          |

- a-3, b-4, c-2, d-1

- a-4, b-1, c-1, d-3

- a-1, b-3, c-4, d-2

- a-2, b-4, c-3, d-1

Ans: D.

#### Flask

Qn: The route() decorator in Flask is used to bind a URL to a function: What is the correct way to bind a URL to a function? (Multiple options may be correct.)

- `@app.route(‘/hello’) def hello_world(): return ‘hello world’` The URL will be as follows:  `http://localhost:5000`.

- `@app.route(‘/hello’) def hello_world(): return ‘hello world’` The URL will be as follows:  `http://localhost:5000/hello`

- `@app.route(‘/’) def hello_world(): return ‘hello world’` The URL will be as follows: `http://localhost:5000/hello_world`

- `@app.route(‘/’) def hello_world(): return ‘hello world’` The URL will be as follows: `http://localhost:5000/`

Ans: B & D.