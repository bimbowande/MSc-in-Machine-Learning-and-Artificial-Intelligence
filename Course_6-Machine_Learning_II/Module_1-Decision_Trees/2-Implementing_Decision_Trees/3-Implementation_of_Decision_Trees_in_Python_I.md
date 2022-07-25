# Implementation of Decision Trees in Python-I

Let’s now implement Decision Trees in Python for a given problem statement. You will be using sklearn for this implementation. You'll be making use of Graphviz to visualise the trees. Hence, go through the instructions for the same.

## Installing Graphviz

Python requires the library 'pydotplus' and the external software, Graphviz, to visualise the decision tree. If you are using Windows, then you will need to specify the path to the pydotplus library in order to access the dot file from Graphviz.

Please refer to the user guide and the steps given below to install Graphviz:

Download [Installation Guide](Docs/Installation_Guides/Graphviz_Installation_Walkthrough.pdf)

**Steps for Windows users are as follows:**

-   Download Graphviz from [here](http://graphviz.gitlab.io/_pages/Download/Download_windows.html) (ZIP file)
-   Unzip the file and copy-paste it in C:\Program Files (x86)\
-   Make sure your file is unzipped and placed in Program Files (x86)
-   Environment Variable: Add C:\Program Files (x86)\graphviz-2.38\release\bin to the user path
-   Environment Variable: Add C:\Program Files (x86)\graphviz-2.38\release\bin\dot.exe to the system path
-   Install the Python Graphviz package - pip install graphviz
-   Install pydotplus - pip install pydotplus

 [Copy the path for Graphviz in your system, in case the above-given path does not work for you.]

  
Instructions to add the environment variable: [click here](https://java.com/en/download/help/path.xml)

```python
# anaconda users
conda install pydotplus

# pip users
pip install pydotplus
```

**Steps for Mac users:**

-   To install the Graphviz on your Mac, you can use Homebrew to:
    -   Install & Download homebrew from [here](https://docs.brew.sh/Installation)
    -   Run this in the terminal

	```python
	brew install graphviz
	```

-   Install pydotplus - pip install pydotplus
-   Install the python graphviz module - pip install graphviz

In the upcoming video, Sajan will explain to you the problem statement and dataset on which you will be implementing this algorithm. You can download the data set below : 

Download [Dataset](Heart_Disease_Case_Study.csv)

**VIDEO**

As you saw in this video, the Decision Tree to be designed has to predict whether a person has heart disease or not. However, for this problem statement, you will be dealing with a small part of this dataset, which will include the following features:

-   id: Patient ID
-   age: Age of the patient (in days)
-   gender: Gender of the patient
-   height: Height of the patient
-   weight: Weight of the patient
-   ap_hi: arterial pressure - upper value
-   ap_lo: arterial pressure - lower value
-   cholesterol: The cholesterol level of the patient
-   gluc: Glucose level in the blood
-   smoke: If the person smokes or not (0/1)
-   alco: If the person drinks alcohol or not (0/1)
-   active: If the person is physically active or not (0/1)
-   cardio: If the person has heart disease or not (0/1)

In this dataset, ‘0’ signifies that the person does not have heart disease, whereas ‘1’ signifies that the person has heart disease. The dataset consists of 14 features. Now, let’s take a look at the next video to understand the data and how to implement decision trees on this.

You can download the python notebook given below:

Download [Python notebook](Heart_Disease_Case_Study)

**VIDEO**

As you saw in this video, you can begin by loading basic Python libraries and the dataset. Then, you can explore the dataset before you start building a Decision Tree. Take a look at the code given below:

```python
#Import libraries 
import pandas as pd
import numpy as np

#Load the Heart Disease dataset
df=pd.read_csv(‘file_location’,sep=';')

#You can view the dataset given below:
df.head()

#Use the following code to view the shape and columns respectively:
df.shape
df.columns

#You can view the statistics using the following code:
df.describe

#You can view the count of people that have a heart disease and those who do not, using:
df['cardio'].value_counts()

#Next, divide the data into input and output columns such that ‘x’ is input columns and ‘y’ is output columns:
y = df['cardio']
x = df.drop('cardio',axis=1)
```

So far in this segment, you have explored the dataset for heart disease case study. In the next segment, you will be creating a Decision Tree for the same.