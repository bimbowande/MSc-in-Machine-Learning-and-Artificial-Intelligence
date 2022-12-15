# Hands On: Branch, Commit, Merge, and Pull

In the previous segment, you created a GitHub account and also configured it. Now, you will learn about the implementation of Git and GitHub in a local system.

The forthcoming video is recorded in the PyCharm Command Line Interface (CLI), although you can simply run the commands in your local Command Line Interface (CLI). We have listed all the commands that have been used in the video.

**VIDEO**

**#**Create a directory with name object-detection. mkdir object-detection **#**Enter into the object-detection directory. cd object-detection/ **#**Create two files train.py and prediction.py in your present working directory i.e. object-detection. type NUL > train.py type NUL > prediction.py **#**Initialize Git. git init **#** Check the status of Git git status **#**Ddd files to Git git add train.py prediction.py **#**Apply commit in Git git commit  -m "Added train and predict files" **#**Apply branching in Git git branch **#**Create new branch new_branch and switch to new_branch from the master branch git checkout -b new_branch **#**Check the branch git branch

Please note that you need to run the command given below when you create a “py” file in the “object-detection” directory in Windows CMD.

**#**Create two files train.py and prediction.py in your present working directory i.e. object-detection. type NUL > train.py type NUL > prediction.py

In the next video, you will learn how to create a repository in Git.

**VIDEO**

You can refer to the commands given below to run in your local CMD.

**#** Change the branch to master. git checkout master **#**Push the master branch to Github or remote repository git push -u origin master **#**Push another branch new_branch to Github git push origin new_branch

In the previous video, you learned how to create a code repository, create a master branch and commit it to GitHub, pushing the changes made to the repository into GitHub.

  
Now, let's go through the definitions of some of the major terms used in the video:

-   **Commit:** It is used to keep track of all the changes made after the last commit. Here, we make changes to the repository and inform Git to put them into the commit. It offers us the functionality to go back to any state of the project at any point.

So, after pushing the code, the next concept we will look at is the pull request, which you are going to learn about in the next video.

**VIDEO**

**#**Pull request git pull origin master

-   **Pull request:**  A pull request alerts the repository owner about the changes that are requested to be made to the code.

With this, we have come to the end of this session. We hope that you now have a thorough understanding of Git and GitHub.

#### Git and GitHub

Qn: Git is a centralized version control system.

- True

- False

Ans: B. *Git is a distributed version control system.*

Qn: Which command should you use to initialize a new Git repository?

- git bash

- git install

- git init

- git start

Ans: C. *This is the correct command to initialize the git.*

Qn: How do you check the state of your local git repository since your last commit?

- git push  

- git status

- git add 

- git fork

Ans:B. *Using git status, you can check the status.*

Qn: How do you stage files for a commit?

- git commit  

- git add

- git reset

- git fork

Ans: B. 

Qn: How do you save the current stage into git version control?

- By committing the staged changes with git commit

- By adding all changes and staging them with git stage 

- By adding all changes and staging them with git add

- By creating a new commit with git init

Ans: A.

