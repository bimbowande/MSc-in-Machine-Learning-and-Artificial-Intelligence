# Flask Framework Demonstration

In the two previous segments, you learned how to build a linear regression model and encapsulate it using pickle. Further, you built HTML code to create a web page to get users’ inputs.

In this segment, you will see how Flask is used to deploy the ML model. In the forthcoming video, you will learn about the deployment of ML models using Flask.

**VIDEO**

One of the most important concepts that you have to understand here is that the “app.py” file works as the orchestration between the “index.html” and the “model.pkl” file. 

Now we will help you understand the app.py files in detail.  
 

```python
app = Flask(__name__)
model = pickle.load(open('model.pkl', 'rb'))
```

In the above lines of code, a Flask application has been created, and the file “model.pkl,” which you generated in the previous segment, has been loaded in the variable “model.”

```python
@app.route('/')
def home(): 
	return render_template('index.html')
```

The above lines of code are used to direct you to the home web page, where you are generally directed when you start your web application.

```python
@app.route('/predict', methods=['POST'])
def predict():
	'''For rendering results on HTML GUI'''
	area = float(request.form.get('area'))
	bedroom = int(request.form.get('bedroom'))
	bathrooms = int(request.form.get('bathrooms'))
	stories = int(request.form.get('stories'))
	guestroom = int(request.form.get('guestroom'))
	basement = int(request.form.get('basement'))
	parking = int(request.form.get('parking'))
	areaperbedroom = float(request.form.get('areaperbedroom'))
	bbratio = float(request.form.get('bbratio'))
	prediction = model.predict([[area, bedroom, bathrooms, stories, guestroom, basement, parking, areaperbedroom, bbratio]])
	output = round(prediction[0], 2)
	return render_template('index.html', prediction_text='The house price predicted is Rupees {}'.format(output))
```

If you look into the above lines of code, you will see that each entry of the web page has been taken either float or int type. 

And ultimately, “prediction” has been assigned this value:

```python
prediction = model.predict([[area, bedroom, bathrooms, stories, guestroom, basement, parking, areaperbedroom, bbratio]])
```

Where “model” is nothing but the file “model.pkl.”

If you are using _host= '0.0.0.0',_ you have to write these lines of code in the file app.py, which is already mentioned on the files given to you:

```python
if __name__ == "__main__":
	app.run(debug=True, host="0.0.0.0")
```

When you run this particular code, you will get a local link in the terminal. When you access the local link in your browser, you will get the web page that you have developed, and this could predict the house price as per your input. You will see this in the next video.

**Note:** If you are running _**host= ‘0.0.0.0’**_, you have to run `http://localhost:5000/` instead of `http://0.0.0.0:5000/`.

**VIDEO**
In this segment, you learned how to develop an end-to-end web application that can run on your local machine. In the next segment, you will learn about Heroku and see how you can use it to make your web application public.

#### Flask Framework

Qn: Consider the following series of steps and arrange them in the order of process that has been followed in the above ‘app.py’:  
a. Serializing the ML model.  
b. Deserializing the ML model.  
c. Creating the flask application.  
d. Running the flask application.  
e. Creating data to the server using the POST method.  
f. Creating a specific URL and mapping it with the function.

- c, a, b, f, e, d

- c, b, f, e, d

- a, b, c, d, e, f

- b, f, c, e, d

Ans: B. *This is the correct order of the steps to build an “app.py” file:*

- *Creating the flask application and deserialization*

- *Creating a specific URL and mapping it with the function*

- *Running the flask application*
