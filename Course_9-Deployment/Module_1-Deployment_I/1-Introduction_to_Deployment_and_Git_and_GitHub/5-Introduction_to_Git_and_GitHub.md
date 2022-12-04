# Introduction to Git and GitHub

In the previous segment, you learned what version control systems are and why they are important. In this segment, you will learn about Git, which is a version control system. 

GitHub is a social code hosting platform where we can look for open-source codes and even make changes. However, it can be accessed only by members, who can even check for the changes made by people to a particular piece of code.

In the forthcoming videos, Abhay will talk about Git and GitHub and explain the various terms associated with them.

**VIDEO**

In this video, you learned that Git is nothing but a version control system, and GitHub is a social code hosting platform:

-   Where you can look up open-source codes and suggest changes, and 
-   That also provides you with the functionality to host websites directly from your repository.

In the next video, we will look at the various terms associated with Git and GitHub.

**VIDEO**

In this video, you learned about the following terminologies:

-   **Repository:** It is a project folder that contains all the information and the code related to a project.
-   **Remote:** It is used for referring to any repository that is hosted on GitHub.
-   **Branch**: The master branch is the stable piece of code that you can show to a client. While you can try to make changes to the branch, you do not change the main branch but its copy. When the change is run successfully, you merge the copy of the branch again with the master branch. The master branch is the version that always works.
-   **Commit:** Committing means you are keeping track of all the changes that you made to a GitHub repository. If you add a feature to your model, you “commit” it to the GitHub repository.
-   **Head:** The topmost commit to any branch is called the head.  

In the next video, you will learn about the rest of the terms related to Git.

**VIDEO**

In this video, you learned about the following terms that help with modifying a repository:

-   **Push:** The transfer of code from the local Git to the remote Git is called a push.
-   **Fork:** Forking is a concept wherein you make a copy of a repository, say, A, on your GitHub account. Let’s call this copy B. Now, to work on this copy, you will need to “git pull” it onto your local machine/local Git and make changes and then push it back to the forked repository B. Now, if you want these changes in B to be merged with the original repository A, then you need to send a pull request. Note that a pull request is different from a git pull. When you use “git pull,” you pull the changes from the forked repository B into your local Git. If you send a “pull request” to the original repository A, you ask their maintainers to pull your changes into theirs (in other words, you ask them to use a “git pull” from your repository B). This process is usually followed when you are contributing to a third-party repository, i.e., you are not one of the contributors of repository A. You will not be able to push the changes directly from the local Git to repository A because you are not a contributor of repository A.
-   **Pull:** Transferring the changes done to the remote repository to the local Git is called pull.
-   **Clone**: You use cloning when you want to duplicate the repository into your local Git. Now, suppose that you are one of the contributors of repository A. In such a case, you do not need to fork A. You can clone repository A directly, which will then be updated to your local Git. You can then make the changes, commit and push them back to the original repository A.

You can go [here](https://stackoverflow.com/questions/3620633/what-is-the-difference-between-pull-and-clone-in-git) to decide when to use “git clone” and “git pull” to make a copy on your local Git.

So, the differences between fork and clone are mentioned below:

1.  Forking creates a copy of a repository on your GitHub account, whereas cloning creates the copy on your local Git.
2.  There is a connection that stays in forking and which can be used to make “pull requests”; this is not the case in cloning. 

In other words, forking is a concept, whereas cloning is a process.

You can refer to the following website to know more about the Git and GitHub terms:

[Terminologies](https://www.javatpoint.com/git-terminology)

You can create your own GitHub account using [this](https://github.com/) link. 

In the next segment, you will have a hands-on using GitHub.

#### Git and GitHub

Qn: Making a copy of the code repository in the GitHub profile is called ______.

- Forking

- Cloning

Ans: A. *When you fork a repository, you create a copy of the original repository (upstream repository) but the repository remains on your GitHub account. Whereas, when you clone a repository, the repository is copied on to your local machine with the help of Git.*

Qn: Which of these Git client commands creates a copy of the repository and a working directory in the client’s workspace?

- Clone

- Update

- Import

Ans: A. *When you clone a repository, the repository is copied on to your local machine with the help of Git.*

Qn: Select the correct version control system type for Git.

- Local version control system

- Centralized version control system

- Distributed version control system

Ans: C. *Git is a distributed version control system. It lets you track changes made to a file and allows you to revert back to any particular change that you wish.*

Qn: What is the difference between Git and GitHub?

Ans: 

- *Git is a version control system that is used to track changes in the source code during software development. It aids in coordinating work among programmers and can be used to track changes in any set of files.*

- *GitHub is a Git repository hosting service; it also adds many of its own features. GitHub provides a web-based graphical interface as well as access control and several collaboration features, basic task management tools for every project.*