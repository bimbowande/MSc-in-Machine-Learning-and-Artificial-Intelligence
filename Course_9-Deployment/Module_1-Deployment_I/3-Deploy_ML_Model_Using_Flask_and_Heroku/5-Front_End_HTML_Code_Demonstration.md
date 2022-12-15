# Front-End HTML Code Demonstration

In the earlier segment, you learned how to encapsulate the ML model using “pickle.” In this segment, you will learn how to develop a front-end dashboard through which users can enter feature details and obtain predictions for the price of a house.

In the forthcoming video, you will learn about the HTML codes.

Play Video

3221820

In the video, you saw that Mithun created a form to get users’ inputs in an HTML file. The “body” of the HTML code is given below.

```html
<body>  <div class="login">    <h1>Predict House price</h1>    <!-- Main Input For Receiving Query to our ML for the fields,  area, bedroom, bathrooms, 'basement', stories, guestroom, parking, areaperbedroom, bbratio-->    <form action="{{ url_for('predict')}}" method="post">      <input type="text" name="area" placeholder="Area" required="required" /><br><br>      <input type="text" name="bedroom" placeholder="Bedroom" required="required" /><br><br>      <input type="text" name="bathrooms" placeholder="Bathrooms" required="required" /><br><br>      <input type="text" name="stories" placeholder="Stories" required="required" /><br><br>      <input type="text" name="guestroom" placeholder="Guestroom" required="required" /><br><br>      <input type="text" name="basement" placeholder="Basement" required="required" /><br><br>      <input type="text" name="parking" placeholder="Parking" required="required" /><br><br>      <input type="text" name="areaperbedroom" placeholder="AreaPerBedRoom" required="required" /><br><br>      <input type="text" name="bbratio" placeholder="BBratio" required="required" /><br><br>      <button type="submit" class="btn btn-primary btn-block btn-large">Predict</button>    </form>    <br>    <br>    {{ prediction_text }}  </div> </body>
```

Here, the header is defined as “Predict House Price.” Using the POST method, you can send to the server the data entered by users in the fields defined as “inputs.”

The are a total of nine inputs, which were obtained after performing some preprocessing on the dataset in the previous segment.

When you open the locally saved file “index.html” in the browser, it will give you this page.  
 
![Predict House Price](https://i.ibb.co/yNGX0Xc/Predict-House-Price.png)

This form will not show any output if you enter values in it. This is because the data has not been input to the ML model as of now. In the next segment, you will learn how Flask is used to orchestrate with the back end and this front-end HTML code to build a web application.

#### HTML

Qn: For the HTML code provided above, you saw that Mithun used the POST method to create data on the server. Do you think you can use the PUT method instead of the POST method here?

- Yes

- No

Ans: A. *Please refer to this Stack Overflow link: [Put vs Post in REST](https://stackoverflow.com/questions/630453/put-vs-post-in-rest)*
