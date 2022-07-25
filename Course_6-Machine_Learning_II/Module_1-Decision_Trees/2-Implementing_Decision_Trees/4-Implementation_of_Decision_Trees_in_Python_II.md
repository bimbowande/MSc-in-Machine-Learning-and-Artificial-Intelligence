# Implementation of Decision Trees in Python-II

Now that you are aware of the dataset and the desired input and output of the Decision Tree, let’s begin creating the decision tree by splitting the data into training and testing data as shown in the next video.

**VIDEO**

In the video given above, in order to create a Decision Tree, you began by dividing the data into train and test data. Then, you created a DecisionTreeClassifier using the training and testing data. You can use the following code to implement the dataset:

#Load the required libraries
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import classification_report, confusion_matrix
from sklearn import metrics

```python
# Divide the data into train and test data such that test data is 20% of the total data as follows:
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2, random_state=0)

# Create a Decision Tree Classifier as follows:
dt_basic = DecisionTreeClassifier()

# Fit the training data in the classifier as follows:
dt_basic.fit(x_train,y_train)

# Make predictions based on the test data using the code given below:
y_preds = dt_basic.predict(x_test)

# You can calculate the accuracy for this code as follows:
accuracy_value = metrics.accuracy_score(y_test, y_preds)
```

So far, you created a Decision Tree and calculated its accuracy. For a better understanding of the model, you can also analyse its confusion matrix. Take a look at the video given below to understand a better way to do so:

**VIDEO**

```python
# You can print the confusion matrix as follows:
confusion_matrix(y_test, y_preds)
```

Recall is an important parameter when it comes to machine learning models. Recall of a model is also known as its sensitivity and measures the number of times an instance is retrieved correctly. Calculate the recall and answer the question given below:

#### Recall

Qn: What is the recall value for this Decision Tree?

- 0.63

- 0.70

- 0.65

- 0.72

Ans: A. *Use the following code to find recall:*

```python
from sklearn.metrics import recall_score
recall_score(y_test, y_preds)
```

*output: 0.6338*

Use the following code to print all the parameters of the confusion matrix clearly:

```python
# Use the following code to print the classification code:
print(classification_report(y_test, y_preds))
```

#### Heart Disease Metric

Qn: Which metric should you track in case of Heart Disease Prediction? Consider 'having heart disease' the class that you are predicting.

- Accuracy

- Recall

- Precision

Ans: B. *You need to cover as many heart patients as you can. If you miss out on anyone, he/she will die because you predicted that the person doesn't have heart disease. Precision can be low because even if you predict someone having heart disease who does not have, the doctor can do second-level verification and dismiss him/ her.*

So far, you created a Decision Tree, found its accuracy and confusion matrix but did not visualise the tree itself. One of the major advantages of Decision Tree is its easy visualisation. Let’s watch the following video and understand how Sajan will visualise the Decision Tree.

**VIDEO**

You can visualise the Decision Tree as follows:

```python
# Load the libraries required for visualisation:
from IPython.display import Image  
from sklearn.externals.six import StringIO  
from sklearn.tree import export_graphviz
import pydotplus, graphviz
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline

# Define the columns on which the Decision Tree is working:
features = list(x.columns[0:])

# Now, you can visualise the data as follows:
dot_data = StringIO()
export_graphviz(dt_basic,out_file=dot_data,feature_names=features,filled=True,rounded=True)
graph = pydotplus.graph_from_dot_data(dot_data.getvalue())
Image(graph.create_png())
```

As you saw above, in this case, if the data is of large amounts, the tree formed is difficult to visualise and prone to overfitting. In the next segment, let’s understand what overfitting is and how to deal with it.