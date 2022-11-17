# Cosine Similarity

In the previous segment, we learnt how to represent meaning in geometric form. Let us understand the cosine similarity between word vectors.

**VIDEO**

The fundamental way of measuring the similarity between two vectors is the cosine similarity.

According to the value of cosine similarity, one can infer several factors about a relations between words:

1.  For smaller θ, the cosine value is close to 1. Such words are called synonymous words.
    
![Synonymous Words](https://i.ibb.co/VHggLvq/Synonymous-Words.png)

2.  For θ=90 and cos(θ)=0 corresponds to unrelated words.

![Unrelated Words](https://i.ibb.co/ZmBrXkF/Unrelated-Words.png)

3.   For θ values where the cosine value is negative, words are called antonyms.

![Antonym Words](https://i.ibb.co/fDZMPDw/Antonym-Words.png)

Now, let’s calculate the cosine similarity between the vectors man and woman from the example discussed in the previous segment. 

**VIDEO**

Let us calculate the cosine similarity of Woman and Man.

![Geometric Representation](https://i.ibb.co/n09vm2P/Geometric-Representation.png)

$$S(Woman,~Man)=cos(\theta)=\dfrac{Woman.Man}{||Woman||||Man||}$$

$$Woman.Man=(2)(2)+(12)(6)$$

$$||Woman||=\sqrt{2^2+12^2}=\sqrt{4+144}=\sqrt{148}$$

$$||Man||=\sqrt{2^2+6^2}=\sqrt{4+36}=\sqrt{40}$$

$$S(Woman,~Man)=\dfrac{76}{\sqrt{148}\sqrt{40}}$$

The cosine similarity of the words man and woman is 0.98776, which indicates that they are closely related. This is an accurate result.

#### Cosine Similarity Question

Qn: What is the cosine similarity between King(8,5) and Queen(8,11)?

- 0.452

- 0.016

- 0.927

- 0.782

Ans: C. $King.Queen=119,||King||=\sqrt{89},||Queen||=\sqrt{185},~S(King,~Queen)=cos(\theta)=\dfrac{119}{\sqrt{89}\sqrt{185}}=0.927$

In the next segment, let us recall the Bag of Words approach that we have learnt earlier.