# API

In the previous session, you learned what deployment is and why it is needed. Then, you learned what a version control system is, why it is important, and how you can work with Git and GitHub. Next, you will gain an understanding of how to deploy using Flask REST API. 
  
Watch the next video to understand what API is.

**VIDEO**

API stands for **application programming interface**. It is a set of protocols and tools that help build software. It is a software intermediary that allows two applications to talk to each other.

Suppose you are using an application on your mobile phone, which connects to the internet and sends data to a server. The server then retrieves that data, interprets it, performs the necessary actions, and sends it back to your phone via the application. The application then presents you with the information that you wanted in a readable way. All of this happens via APIs.

Let's consider a more familiar example to understand APIs better.

Suppose you are sitting at a table in a restaurant, holding the menu. The kitchen is a part of the 'system' that will prepare your food. What is missing is the important link to communicate your order to the kitchen and deliver your food to your table. This is where the waiter comes into the picture, who, in this example, is an API. In other words, the waiter is the messenger, or API, that takes your request or order and tells the kitchen, that is, the system, what to do. Then, the waiter delivers the response to you, which, in this case, is the food.

Let's take the example of 'Paytm' to book flight tickets. Paytm aggregates information from a number of airline databases. It interacts with an airline’s API and seeks information from the airline’s database to book seats, select baggage options, etc. The API then takes the airline’s response and delivers it right back to Paytm, which then shows you the updated and relevant information.

Having understood this, you now need to learn about the REST framework that facilitates API communication.

#### APIs

Qn: Which of the following statements are true regarding APIs?

- API stands for application performance interface.

- An API helps in the communication and data exchange between two software systems.

- An API receives a request from a source, takes that request to the database, fetches the requested data from the database, and returns a response to the source.

Ans: B & C.