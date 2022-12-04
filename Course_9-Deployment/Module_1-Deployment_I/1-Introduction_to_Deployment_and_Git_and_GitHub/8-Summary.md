# Summary

Let's summarize the key takeaways from this session.

-   **Machine learning pipeline:** The topic of machine learning pipeline can be grouped under the following heads:

1.  Data acquisition
2.  Data analysis
3.  Exploratory data analysis
4.  Feature engineering
5.  Model training
6.  Evaluation

-   **Concept drift:** Consider an example where people are buying products from an online platform. The buying behavior of the customers may change with time. Suppose you have built a model that predicts sales based on input parameters like money spent on marketing and promotions being run.  The model is likely to become less and less accurate over time; this is known as concept drift. In the merchandise sales application, one reason for a concept drift may be seasonality, which means shopping behavior changes seasonally. For example, the winter holidays season witnesses higher sales compared with the summer holidays season, which witnesses lower sales. Hence, the model needs to keep updating with the concept drift.
-   **Software architecture of deployment:** Let's try to understand how to query into a particular website to get results. Suppose you want to get some information from a website. This task will be carried out through the following steps:

1.  The user would request some information.
2.  The user’s request would go through a web framework.
3.  This framework would help you interact with the machine learning model.
4.  The machine learning model would then make predictions and respond to the user.

A machine learning model, once deployed, goes through these steps. Once the model predicts the results, it sends the predictions back to the user through the web framework.

The image given below depicts these steps.

![Software Architecture of Deployment](https://i.ibb.co/41g1GHL/Software-Architecture-of-Deployment.png)

-   **Version control systems:** A version control system: 

1.  Can keep a track of all the changes made;
2.  Can also revert to stable versions irrespective of the number of changes made; and
3.  Should also allow people to collaborate as a team, without affecting anyone’s work, and merge all the changes to a stable version.

-   **Git and GitHub:** You learnt that Git is nothing but a version control system, and GitHub is a social code hosting platform:

1.  Where you can look up open-source codes and also suggest changes to them, and 
2.  That also provides you with the functionality of hosting websites directly from your repository.

The various terms associated with Git and GitHub are listed below:

1.  Repository
2.  Remote
3.  Branch
4.  Commit
5.  Head
6.  Push
7.  Fork 
8.  Pull clone

After that, you got some hands-on experience with Git and GitHub.

Please note that we did not cover everything on GitHub in this session. You can refer to the following links to learn more about some other popular functions and terms:

[Additional Reading I](https://www.javatpoint.com/git-terminology)

[Additional Reading II](https://git-scm.com/docs/git#_git_commands)

[Additional Reading III](https://www.toolsqa.com/category/git/)
