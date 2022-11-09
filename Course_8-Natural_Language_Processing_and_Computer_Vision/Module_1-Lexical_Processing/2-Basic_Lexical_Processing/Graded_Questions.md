# Graded Questions

The following questions are **graded**.

Qn: The frequency of words in any large enough document (assume a document of more than, say, a million words) is best approximated by which distribution:

- Gaussian distribution

- Uniform distribution

- Zipf distribution

- Log-normal distribution

Ans: C. *Word frequency is best approximated by this kind of distribution.*

Qn: Which of the following words can’t be reduced to its base form by a stemmer:

- Bashed

- Successful

- Worse

- Sweeping

Ans: C. *The base form of the word ‘worse’ is ‘bad’. ‘Worse’ can’t be reduced to ‘bad’ using a stemmer.*

Qn: Due to some error in the back end of an information collection system, noise has been introduced in all the text collected. A prefix of "SKS" has been added to the names of all the people who interacted with the collection system. 

Which of the following is the right regex to eliminate the prefix.

- `text = re.sub("(sks)+","", text)`

- `text = re.sub("(SK)+","", text)`

- `text = re.sub("(SKS)+","", text)`

- `text = re.sub("(SKS)+", " ", text)`

Ans: C. *This will match the prefix and remove it correctly.*

Qn: Which of the following inputs are needed when you find the lemma of a given word when you perform lemmatization using the NLTK library?  More than one option may be correct.

- The word itself 

- Part of speech 

- A set of rules that dictate the modifications needed to find the lemma

- All of the above.

Ans: A & B. *Any change in the part of speech will have an impact on the lemma of the word. Therefore, this is another input that is needed for lemmatization.*
