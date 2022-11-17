# Geometric Representation of Meaning

In the previous segment, you learnt that syntactics alone is not sufficient to understand the natural language. Distributional semantics lets you capture the meaning of the word as vectors. The different aspects of meaning can be captured using geometry. In the next video, this will be covered.

**VIDEO**

Now, let’s try to capture the meaning of a word using geometry. Let’s consider two dimensions, speciality and femininity, to represent the meaning of the word. A classic example of this would be plotting the words King, Queen, Man and Woman on a plot of Speciality vs Femininity. 

A King and Queen are equally special; however, a Queen is more feminine than a King. Similarly, a man is as special as a woman, but a woman is more feminine than a man. Interestingly, a man/woman is not as special as a king/queen. With all this in mind, the plot would look something like this.

![Geometric Representation](https://i.ibb.co/n09vm2P/Geometric-Representation.png)

Note that the meaning of the word is restricted to only two features; hence, this is not the complete picture. However, this gives an intuitive understanding of how the meaning of words are represented in geometry.

After converting words into vectors, the next step is to perform vector arithmetic!

**VIDEO**

The movement from a woman to a queen is simply an increase in the speciality with relatively the same femininity. 

On the other hand, the movement from a man to a woman is an increase in femininity with relatively the same speciality.

These transformations correspond to vector addition and subtraction to capture the shift in terms of a vector. A major advantage of representing words as vectors is the ability to compare them through the vector operations depicted above. 

In the next segment, you will learn about Cosine Similarity.