# Deploy the ML Model

In the previous segment, you created the Docker image and pushed it into the Amazon ECR that you created earlier.

Now, let’s deploy the application using kubectl CLI.

**VIDEO**

-   To deploy and manage applications on a cluster, you need to communicate with the Kubernetes cluster management system. Execute the following command to deploy the application:

```shell
kubectl create deployment iris-app --image=ECR_URL_COPIED_FROM_ECR_REPOSITORY:v1
```

-   In the next step, you need to expose your application to the Internet. By default, the containers that you run on are not accessible through the Internet because they do not have external IP addresses. Execute the following code to expose the application to the Internet:

```shell
kubectl expose deployment iris-app --type=LoadBalancer --port 5000 --target-port 5000
```

-   To find the URL that needs to be used to run the web application, type the following code:

kubectl get services

You will receive the URL that will be used for running the web application. In the next video, you will run the web application using the Jupyter Notebook.

**VIDEO**

-   After copying the URL that you obtained from the ‘get service’ command, you need to open your Jupyter Notebook in your local system and copy the following lines of code:

```python
import json
import requests
url = "http://URL_COPIED_FROM_ABOVE_VIDEO:5000/predict"
data = json.dumps({'sl': [5.84, 4.38], 'sw': [3.0, 2.16], 'pl': [3.75, 7.65], 'pw': [1.1, 1.23]})
r = requests.post(url, data)
print(r.json())
```

Here, since you are giving two inputs simultaneously in the array format, you will get two outputs accordingly.

So for   
**Iris-1: Sepal length= 5.84, Sepal width= 3.0, Petal length= 3.75 and Petal width= 1.1  
Iris-2: Sepal length= 4.38, Sepal width= 2.16, Petal length= 7.65 and Petal width= 1.23**

When you run the code given above, you will get [1, 0] as the output, which means that Iris-1 is predicted as Iris Versicolor and Iris-2 is predicted as Iris Setosa.

With this, you have deployed an ML model on the Kubernetes cluster. If you observe carefully, you did not create any HTML page here. In the next segment, your web application page will be ready and can be accessed without using the Jupyter Notebook.