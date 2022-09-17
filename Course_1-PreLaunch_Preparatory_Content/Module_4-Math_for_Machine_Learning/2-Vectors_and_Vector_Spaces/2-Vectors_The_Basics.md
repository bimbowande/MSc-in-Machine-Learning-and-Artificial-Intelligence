# Vectors: The Basics

When you think about vectors, you can probably recall "magnitude and direction". In general, there are two main ways to think about vectors. People often prefer one over other according to their discipline of study.

## **Vectors: Two Different Views**

The first view of vectors is **algebraic**, where you see **vectors as** **ordered lists** **of objects**.  For example, let's say there are 10 students whose marks you wish to store in a single object. You can express this in the form of a vector →m

$\overrightarrow{m}=[78, 87, 65, 74, 56, 90, 85, 79, 62, 70]$

This is a vector with 10 values. These can be denoted by m1,m2,m3,... which are called the individual **entities** (or elements) of the vector. This is often the preferred view of computer scientists.

The second view of vectors is **geometric**, where you visualise **vectors as arrows in a 2D or a 3D plane.** This is the view you remember from your physics class - arrows which have **magnitude and direction.**  Examples of quantities having a magnitude and direction are velocity, gravitational force, magnetic field etc.

On the other hand, quantities such as mass, distance between two points, the volume of a liquid etc. do not have a direction but only magnitude. They are called **scalars**.

## **Video**

[Here is a youtube video courtesy 3Blue1Brown that helps you visualise the basic concepts of vectors.](https://www.youtube.com/watch?v=fNk_zzaMoSs)

Some basic terminologies related to vectors are summarised below. You should be able to recall these just by reading, though if you prefer a more detailed refresher, you can go through the [first 5-6 videos of this Khan Academy playlist](https://www.youtube.com/watch?v=br7tS1t2SFE&list=PLRiaIeW3IkTUcrivMs8P955VSjTjHW5ot&index=1):

- Vectors are usually represented in two ways - as ordered lists, such as a=[1,2,3], or using the 'hat' notation, such as $a=\hat{i}+2\hat{j}+3\hat{k}$. In this case, $\hat{i}, \hat{j}, \hat{k}$ represent the three perpendicular directions (or axes).
- The number of elements in a vector is the **dimensionality** of the vector. For e.g. a=[1,2] is two dimensional (2d) vector , a=[1,2,3] is a 3d vector and so on.
- The **magnitude** of a vector is the distance of its tip from the origin. For an n-dimensional vector $a=[a_1, a_2, \dots, a_n]$, the magnitude is given by $||a||=\sqrt{a^2_1+a^2_2+\dots+a^2_n}$. For example, the magnitude of $a=[1,2,3]$ is $||a||=\sqrt{1+4+9}=\sqrt{14}$.
- A **unit vector** is one whose distance from the origin is exactly 1 unit. For e.g. the vectors$\hat{i},\hat{j},\dfrac{\hat{i}}{\sqrt{2}}+\dfrac{\hat{j}}{\sqrt{2}}$ are unit vectors.

#### Magnitude of a Vector

Qn: The magnitude of the vector a=[1,0,2,−1] is:

- $\sqrt{2}$

- $\sqrt{6}$

- 2

- $\sqrt{3}$

Ans: B. *The magnitude is $\sqrt{1+0+4+1}=\sqrt{6}$.*

In the next segment, you will learn how vectors can be combined with each other to create new vectors, and what those combinations actually represent.
