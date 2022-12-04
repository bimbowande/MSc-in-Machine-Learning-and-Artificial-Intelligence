# Graded Questions

#### Graded Questions

Qn: Which of these statements about the pickling of an object is/are true? (**Note:** More than one statement may be true.)

- The function `dump()` is called to serialize an object hierarchy.

- The function `load()` is called to deserialize a data stream.

- The function `dump()` is called to deserialize a data stream.

- The function `load()` is called to serialize an object hierarchy.

Ans: A & B. *`pickle.dump(arg_1, arg_2)` is used to save a model to disk. `pickle.loads(arg_1, arg_2)` is used to deserialize a model from disk.*

Qn: You went through the entire session and saw that when you run the file “app.py,” you get a URL to run the web application in local. A code of app.py is given below:

```python
import numpy as np 
from flask import Flask, request, jsonify, render_template 
import pickle 

app = Flask(__name__) 

model = pickle.load(open('model.pkl', 'rb'))

@app.route('/') 
def home(): 
    return render_template('index.html')   

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
    prediction = model.predict([[area, bedroom, bathrooms, 
							     stories, guestroom, basement, 
							     parking, areaperbedroom, bbratio]])
    output = round(prediction[0], 2)
    return render_template('index.html', prediction_text='The house price predicted is Rupees {}'.format(output))   

if __name__ == "__main__":
    app.run(debug=True)

```

Suppose you get URL_1 when you run the file "app.py." When you enter values in the fields and press the “Submit” button, you get URL_2. What will be the value of URL_1 and URL_2?

- URL_1 and URL_2 have the same value, which equals `http://127.0.0.1:5000/`.

- URL_1 and URL_2 have the same value, which equals `http://127.0.0.1:5000/predict`.

- **URL_1:** `http://127.0.0.1:5000/`  and **URL_2:** `http://127.0.0.1:5000/predict`

- **URL_1:** `http://127.0.0.1:5000/predict` and **URL_2:** `http://127.0.0.1:5000/`

Ans: C.

Qn: Which of these options about the types of services is/are correct? (**Note:** More than one option may be correct.)

- **AWS EC2 and S3:** IaaS

- **Google Apps:** SaaS

- **Heroku and RDS:** PaaS

- **Google apps, Heroku:** PaaS

Ans: A, B & C. *EC2 and S3 are classified under infrastructure as a service. Google apps is software. Hence, it is a service. Heroku and RDS are platforms that provide services.*

Qn: Which of these options is not a service managed by a server in the case of IaaS?

- Data

- RunTime

- OS

- Storage

Ans: D. *Storage is not a service managed by a server in the case of IaaS.*
