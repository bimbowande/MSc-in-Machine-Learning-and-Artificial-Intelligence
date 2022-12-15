# Creating a Web Application Using Heroku

In the earlier segment, you learned that Heroku is categorized under PaaS (platform as a service), and it helps developers to build, run, and operate applications entirely in the cloud. 

In the forthcoming video, you will learn how to deploy an ML model using Heroku. We suggest that you follow all the steps for an in-depth understanding of the deployment of ML models using Heroku.

**VIDEO**

To deploy an ML model using Heroku, you should have these two files ready:

-   **Procfile:** It is also called the procedure file.
-   **requirements.txt:** It contains the version requirement of all the libraries and tools that are essential for model deployment.

You have to inform Heroku, which is a platform as a service, about the OS and the different versions of the various applications that are required to deploy a model. All of this information is present in the file “requirement.txt.” If you look at the file “requirement.txt,” you will notice that it contains these tools and libraries:

```python
Flask==1.1.1 
gunicorn==19.9.0 
itsdangerous==1.1.0 
Jinja2==2.10.1 
MarkupSafe==1.1.1 
Werkzeug==0.15.5 
numpy>=1.9.2 
scipy>=0.15.1 
scikit-learn>=0.18 
matplotlib>=1.4.3 
pandas>=0.19
```

All the aforementioned tools and libraries are relevant to deploy ML models, and their versions are mentioned in this file.

Another file is the “Procfile” or the procedure file. In this file, you specify that it is a web application and a running HTTP server, which is Gunicorn in this case. Gunicorn is a Python HTTP server. 

You can learn more about Gunicorn at this link:

-   [Gunicorn](https://devcenter.heroku.com/articles/python-gunicorn)

Before you deploy an ML model using Heroku, you have to create your own GitHub account so that you can load all the files in a repository on GitHub.

Please refer to this link to create a GitHub account:

-   [Create a GitHub account](https://github.com/)

**Once you have created a GitHub account, run these repository files in Heroku:**

-   [**Git repository to run using Heroku**](https://github.com/antrikshsaxena/moon)

You need to download all the files from the above Git repository and then create you brown repository and add the files to it. Once you have copied all the files to your repository, you can then access the repository from Heroku. This is demonstrated in the next video.

**VIDEO**

Here are the steps that you need to follow to work with the Heroku CLI:

-   **Open Heroku's website:** [Heroku's website.](https://dashboard.heroku.com/)
-   Create an account on Heroku.
-   Create a new application and give it a unique name.
-   Before going to deploy a model using GitHub, let's first try to understand the Heroku CLI.
-   Download and install the Heroku CLI from this link: [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).
-   Go to your terminal and type “_heroku login_.” This will get you back to the Heroku CLI login page. Now you can access Heroku logs using your terminal only.

In the next video, you will learn how to deploy an ML model using a GitHub repository.

**VIDEO**

Here are the steps that you need to follow to work with Heroku using GitHub:

-   Log into your GitHub account.
-   Make sure you have added all required files to the repository, as shown in the above video (you are already given all the files that are required to deploy this particular model).
-   Next, mention the name of the GitHub repository in Heroku to connect with GitHub.
-   Further, press the “Deploy Branch” button to deploy the model.
-   Next, click on the “View” button to open the web application in your browser.

You have thus deployed your model using Heroku.   
 
You can also see the logs of the deployment process using the Heroku CLI. To do that, you need to simply enter the command “heroku logs” or “heroku logs -a #application_name” in your terminal.

In this segment, you learned that the Heroku CLI plays an important role when you get any error in the entire process of deployment using Heroku.

#### Heroku

What Is Heroku?  

- IaaS

- PaaS

- SaaS

- On-Premises

Ans: B. *Heroku is a platform to deploy models.*
