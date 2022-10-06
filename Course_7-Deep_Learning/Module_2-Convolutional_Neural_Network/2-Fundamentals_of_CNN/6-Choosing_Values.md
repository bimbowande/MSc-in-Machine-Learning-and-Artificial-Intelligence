# Choosing Values

You learnt that you have multiple parameters associated with the convolution process, which are listed below:

-   Filter size
-   Stride
-   Padding

However, you cannot convolve the images with just any combination of these attributes. You need to alter them based on your input image and the required output from the architecture. Let’s understand this aspect in more detail in the upcoming video.

**VIDEO**

As mentioned in this video, you cannot convolve a 6×6 image with a 3×3 filter using a stride of 2. Let’s revisit the formula that is used to calculate the output size using the input size, filter size, padding and stride length. 

We are given the following sizes:

-   Image - **n × n**
-   Filter - **k × k**
-   Padding - **p**
-   Stride - **s**

After padding, we get an image of size **(n+2p),(n+2p)**. After we convolve this padded image with the filter, we get:

Size of convolved image = $\left(\dfrac{n+2p−k}{s}+1\right),~\left(\dfrac{n+2p−k}{s}+1\right)$

This also leads to another important conclusion. As the output size cannot be a fraction, the value (n+2p−ks). Therefore, you can select the values of k, p and s appropriately using the aforementioned condition.

**Convolution over 3D images**  
So far, you have learnt how to apply convolution only on 2D arrays. However, most images are coloured, and thus, comprise multiple channels (such as RGB). They are generally represented as a 3D matrix of size ‘**height x width x channels**’. However, the convolution process does not change with the inclusion of the third dimension. To convolve such images, you simply use **3D filters**. The basic process of convolution is still the same: You take the element-wise products and sum up their values. 

The only difference is that now, the filters will be 3D, such as 3×3×3 or 5×5×3. In these examples, the last ‘3’ indicates that the filter has as many channels as the image. For example, if you have an image of size 224×224×3, you can use filters of sizes 3×3×3, 5×5×3, 7×7×3, etc. (with appropriate padding).

![Choosing Values](https://i.ibb.co/wQLMRkJ/Choosing-Values.jpg)

  
Here, instead of 9 ‘3×3’ values, the filter will now hold 27 ‘3×3×3’ values. In the next segment, you will understand how to determine these values in order to extract a feature from the image. 

#### Stride

Qn: Given an input image of size 224x224, a filter of size 5x5 and padding of 3, what are the possible values of stride S?

- 1

- 2

- 3

- 4

Ans: A & C. *(n+2P-k) should be divisible by stride 's'. So, (224+ 2x3 - 5) = 225. should be divisible by any possible values.*

#### Padding

Qn: Given an input image of size 224x224, a filter of size 5x5 and stride of 2, what are the possible values of padding?

- 1

- 2

- 3

- Not possible

Ans: D. *(n+2P-k) should be divisible by stride 's'. So, (224 + 2xPadding -5) should be divisible by 2. This is not possible for any value of padding.*

#### Output Size

Qn: The tables below enlist some combinations of the input size, filter size, stride length, padding and the output size. Match the rows in the left table corresponding to the outputs in the right table: (One or more options may be correct)

![Choosing Values Output Size Qn](https://i.ibb.co/tp8zBgZ/Choosing-Values-Output-Size-Qn.png)

- a->d, b->e, c->f 

- a->e, b->d, c->f 

- a->e, b->f, c->d

Ans: C. *Calculate the output size using ((n+2P-k)/S +1, (n+2P-k)/S) +1).*

#### Padding and Output Size

Qn: Doing convolution without padding (assume that you are using a normal convolution with a k x k filter without shrinking it towards the edges etc.) : 

- Always reduces the size of the output

- Reduces the size of the output only when the stride length is greater than 1

Ans: A. *Doing convolutions without padding always reduces the output size. You can see that from the formula as well: (n - k)/s will be less than n for all positive values of k.*

