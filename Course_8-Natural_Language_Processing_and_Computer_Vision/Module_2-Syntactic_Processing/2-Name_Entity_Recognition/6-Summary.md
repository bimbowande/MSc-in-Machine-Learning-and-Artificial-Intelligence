# Summary

This session covered the following topics and concepts:

-   Name Entity Recognition: NER is the technique to identify the entities in the corpus. It helps you easily identify the key elements in a text, such as a person’s names, location, brands, monetary values and dates. You got a better understanding of commonly used entity types such as the following:  
    - PER: The name of the person (John, James, Sachin Tendulkar)  
    - GPE: Geopolitical entity (Europe, India, China)  
    - ORG: Organisation (WHO, upGrad, Google)  
    - LOC: Location (River, forest, country name)

Then, you have learnt about a simple rule-based technique that can be used to create a NER model.

**Simple rule-based NER tagger:** Another approach to build a NER system is by defining simple rules such as the identification of faculty entities by searching ‘PhD’ in the prefix of a person’s name.

These rules are not complete by themselves. It only works on some selected cases, and there will always be some ambiguity in such rules. 

Hence, to overcome these two issues, **machine learning** techniques can play a vital role in detecting named entities in the text.

-   **NER a Sequence Labelling Problem and IOB tags:** Instead of using nouns, verbs, etc., we will use the inside-outside-beginning (IOB) tags for entities that provide more relevant information about the text.

Refer to the following example for IOB labelling.

Consider a sentence ‘S’ as **‘Donald (B-PER) Trump (I-PER) visit (O) New (B-GPE) Delhi (I-GPE) on (O) February (B-DATE) 25 (I-DATE) , (I-DATE) 2020 (I-DATE)’**

-   **Python demonstration of NER:** Similar to PoS tagging, you can also find a named entity in the sentence using the following code.

```python
import spacy # import spacy module
model = spacy.load("en_core_web_sm") #load pre-trained model
doc = "##Any sentence"
 
processed_doc = model(doc); #process input and perform NLP tasks
for ent in processed_doc.ents:
print(ent.text, " -- ", ent.start_char, " -- ", ent.end_char, " -- ", ent.label_)
```

