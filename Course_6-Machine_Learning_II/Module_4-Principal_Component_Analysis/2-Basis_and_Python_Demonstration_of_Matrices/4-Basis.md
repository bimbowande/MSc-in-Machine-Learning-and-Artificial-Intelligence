# Basis

In this segment, you will learn about another essential building block of the PCA algorithm called ‘**Basis**’. 

Suppose there is a hospital that maintains the health records of patients in terms of temperature, height, weight, heart rate, blood pressure, etc. Let’s consider only two parameters, i.e. weight and height, for our purpose. 

Suppose there is a patient whose height is 165 centimetres (cm) and weight is 55 kilograms (kg). In the FPS system of units, you can measure the height as 5.4 feet (ft) and weight as 121.3 pounds (lbs). One thing that you would notice here is that whether you represent the height in centimetre or feet, the height remains the same. This is what the concept of basis is about. 

Suppose you have the details of the height and weight of 100 patients. You can locate each patient on an x-y plane as a vector, where the x-axis is weight in ‘kg’ and the y-axis is height in ‘cm’. So, here, the basis will be ‘kg-cm’.  
 

Now, suppose you want to locate the height and weight of each patient in the ‘ft-lbs’ system. For this, you need to have a new axis where ‘lbs’ is on the horizontal axis and ‘ft’ is on the vertical axis. So, here, the basis will be ‘lbs-ft’.

Let’s understand the concept of basis in the next video.

**VIDEO**

Now, let’s learn about the ‘basis vectors’.

Let’s consider the patient dataset example again, where the height is in ‘cm’ and the weight is in ‘kg’. Suppose there is a patient whose height is 165 cm and weight is 55 kg. You have a vector ‘v’, which represents this information on an x-y plane where the basis is kg-cm.  

$v=\begin{bmatrix}165\\55\end{bmatrix}$

The vector ‘$v$’ can be represented in a linear combination of two basis vectors $b_1$ and $b_2$:
$$\begin{bmatrix}165\\55\end{bmatrix}=165\begin{bmatrix}1\ cm\\0\ kg\end{bmatrix}+55\begin{bmatrix}0\ cm\\1\ kg\end{bmatrix}$$
Where $b_1$ and $b_2$ are:

$b_1=\begin{bmatrix}1\\0\end{bmatrix}$,  $b_2=\begin{bmatrix}0\\1\end{bmatrix}$

The points regarding the basis and basis vectors are summarised below:

-   ‘Basis’ is a fundamental unit that defines the space in which you express vectors.
-   In any dimensional space or matrix, vectors can be represented as a linear combination of basis vectors.
-   The basic definition of basis vectors is that they are a certain set of vectors whose linear combination is able to explain any other vector in that space. 
-   Space can be defined by infinite combinations of basis vectors.

As you know that 1 ft is equal to 30.48 cm and 1 lb is equal to 0.45 kg, the height and weight of 165 cm and 55 kg, respectively, can be represented in the following format.

$$\begin{bmatrix}165\\55\end{bmatrix}=165\begin{bmatrix}1\\0\end{bmatrix}+55\begin{bmatrix}0\\1\end{bmatrix}=5.4\begin{bmatrix}30.48\\0\end{bmatrix}+121.3\begin{bmatrix}0\\0.45\end{bmatrix}$$
  
Where 165 cm is equivalent to 5.4 ft and 55 kg is equivalent to 121.3 lbs. Hence, you have learnt

to convert the basis from kg-cm to lbs-ft.

Please note that the change of basis is not only the unit change, it is something different though the unit change comes under that category of basis change. You will have a better idea about the change of basis from the next segment.

In the next segment, you will learn how to change the basis.

**Comprehension:**

Suppose you have data on crude oil tanks. This data contains the volume, density and weight of the tanks, which are represented in a litre, kg/L and kg, respectively.

You have been given the following relations:  
1 litre = 0.001 cubic metre  
1 kg/L = 10,00,000 grams/cubic metre  
1 kg = 1,000 grams

Assume the measurements of a tank are 10 L, 0.01 kg/L and 0.1 kg.

#### Basis

What will be the correct linear equation to represent the basis change from L, kg/L and kg to cubic metre, grams/cubic metre and grams?

- ![Basis Question 1](https://i.ibb.co/5YJFtfw/Basis-Question-1.png)

- ![Basis Question 2](https://i.ibb.co/t26bP1N/Basis-Question-2.png)

- ![Basis Question 3](https://i.ibb.co/SR9SWBx/Basis-Question-3.png)

- ![Basis Question 4](https://i.ibb.co/93c67rL/Basis-Question-4.png)

Ans: A. *The relations are given as follows:  1 cubic metre = 1,000 L; 1 grams/cubic metre = 0.000001 kg/L; 1 grams = 0.001 kg. Hence, based on these relations, this option is correct.* 

Qn: What will be the value of 0.01 kg/L in grams/cubic metre?

- 1000

- 10000

- 100000

- 1000000

Ans: B. *This option is correct, as the linear equation for the basis change is:*
$$\begin{bmatrix}0\\0.01\\0\end{bmatrix}=0\begin{bmatrix}10^3\\0\\0\end{bmatrix}+10^4\begin{bmatrix}0\\10^{-6}\\0\end{bmatrix}+0\begin{bmatrix}0\\0\\10^{-3}\end{bmatrix}$$
