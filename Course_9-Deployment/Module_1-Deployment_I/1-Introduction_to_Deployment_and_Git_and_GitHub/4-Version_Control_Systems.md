# Version Control Systems

In earlier segments, you learned about the machine learning pipeline, the need for deployment, as well as the different steps followed by models when they are deployed.

But so far, we have considered that only one contributor is writing the code for the model. Now, suppose 10 people are contributing to this instead of one. If one of them makes some changes to the code, then how do we make sure that all the others working on the code do not make the same changes again?

This is where **version control systems** come into the picture. It is quite an important topic to cover, as you will be working in groups in the capstone; this will help you keep track of changes.

In the forthcoming video, we will listen to Abhay as he explains how a version control system helps us solve this problem.

**VIDEO**

Suppose you want to show a demo of your model to a client. Your model is running well right now, but you want to add a few new features to it. You write a thousand new lines of code since the last version, but your code is not working now. This is when you need a system that can keep track of all the changes that you had made to the model and revert back to the stable version in case the new version is not working. This system is known as a version control system.

The need for a version control system can be summarized as follows:

-   When working on any project, we need to manage our project files, i.e., keep track of the entire history of the things that we are working upon.
-   When we are working on a project as a team, we start with building a basic version of the project, followed by continuous feature developments for improving the project.
-   In this whole scenario, errors are highly likely to occur during development, and we might need to go to the previous stable version.

This is where we feel the need for a system that:

1.  Can keep track of the all changes made;
2.  Can also revert to stable versions irrespective of the number of changes made; and
3.  Should also allow people to collaborate as a team, without affecting anyone’s work, and merge all the changes to a stable version.

These tasks are handled through a **version control system**.

You can refer to the following website to know more about version control systems:

[Version control system](https://www.geeksforgeeks.org/version-control-systems/#:~:text=Version%20control%20systems%20are%20a,(snapshots)%20of%20the%20project.).

In the next few segments, you will learn about Git, which is a version control system, and GitHub.

#### Version Control System

Qn: Which of the following is not a feature of a version control system?

- It keeps track of all the changes made.

- It does not allow to work in a collaborating manner by different team members.

- It allows collaborating as a team and merges all changes to a stable version.

- Multiple people can work simultaneously on a single project. Everyone works on and edits their own copy of the files, and they decide when to share the changes made by them with the rest of the team.

- Version control does not provide access to a project's version history.

Ans: B & E. *It should allow collaborating as a team without affecting anyone's work and merge all changes to a stable version. It provides access to a project's version history.*

Qn: Match the following.

|                                       |                                                                                                                                             |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| a. Local version control system       | 1. It contains one repository, and each user gets their own working copy. All the changes in the files are tracked under the single server. |
| b. Centralized version control system | 2. It contains multiple repositories. Each user has their own repository and working copy.                                                  |
| c. Distributed version control system | 3. It maintains track of files within the local system. It keeps patch sets (differences between files) in a special format on disk.        |

Which of the following options is correct?

- a-1, b-3, c-2

- a-3, b-1, c-2

- a-2, b-1, c-3

- a-1, b-3, c-2

Ans: B. *This is the correct option. You can refer to the following link to get a better idea of this. [Types of version control systems](https://blog.eduonix.com/software-development/learn-three-types-version-control-systems/)*

