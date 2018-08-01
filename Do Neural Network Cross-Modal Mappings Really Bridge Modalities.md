# Do Neural Network Cross-Modal Mappings Really Bridge Modalities?

|||
| --- | --- |
| Title | Do Neural Network Cross-Modal Mappings Really Bridge Modalities? |
| Authors | Guillem Collell and Marie-Francine Moens |
| Year | 2018 |
| URL | https://arxiv.org/pdf/1805.07616.pdf |


Cross-modal models map image embeddings to language embeddings, and vice versa. 
This is usually achieved with feed-forward neural networks. Collell and Moens show
this vision-to-language (or language-to-vision) mapping is often less effective
than it should be. 
 
Two experiments prove this: 

- First, the mapped vectors share more nearest neighbours with the
original vectors than with the target vector of the mapping. 
- Second, even untrained mappings appear to preserve the semantic structure 
of the input embeddings. For example, similarities between GloVe 
vectors that are mapped to the visual mode with an untrained network sometimes 
correlate better with human word similarity judgements
than similarities between the original GloVe vectors. 

These results suggest cross-modal
mappings do not yet succeed in making the neighbourhood structure of the mapped
embeddings similar to that of the target vectors.
