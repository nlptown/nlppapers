# Delete, Retrieve, Generate: A Simple Approach to Sentiment and Style Transfer

|||
| --- | --- |
| Title | Delete, Retrieve, Generate: A Simple Approach to Sentiment and Style Transfer |
| Authors | Juncen Li, Robin Jia, He He, Percy Liang |
| Year | 2018 |
| URL | https://arxiv.org/abs/1804.06437 |


Text attribute transfer is the task where one attribute of a sentence has to be altered (e.g.
its polarity), but its attribute-independent content has to be kept. Li et al. propose
a solution to this challenge that only needs sentences labelled with their attribute as 
training data. 

Their three-step approach proceeds as follows: 

1. Delete: They identify attribute n-gram markers by their relative frequency in sentences
labelled with that attribute, compared to sentences without that attribute. To change
the attribute of a sentence, they first delete all such markers whose relative frequency
exceeds a certain threshold.

2. Retrieve: Next, they retrieve sentences of similar content that display the target attribute, 
based on tf-idf word overlap score.

3. Generate: Finally, they generate the new sentence. Their most successful method does
this by 

    - first encoding the target sentence without attribute markers (from step 1) with one RNN, 
    - then encoding the sequence of attribute markers from the retrieved sentence with another RNN,
    - and finally decoding the concatenated result to the final target sentence.

This model is trained as a kind of denoising auto-encoder whose task is to reconstruct 
a sentence based on its content words on the one hand and its (randomly altered) attribute 
markers on the other. 

Evaluations by human raters on data sets with reviews (from Yelp and Amazon) and captions 
show Li et al.'s method outperforms all existing competitors. This means they return 
successful sentences (i.e. grammatical sentences with the right attribute) between 29%
(for reviews) and 43% (for captions) of the time.

