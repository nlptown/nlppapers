# Neural Text Generation from Structured Data with Application to the Biography Domain

|||
| --- | --- |
| Title | Neural Text Generation from Structured Data with Application to the Biography Domain |
| Authors | Rémi Lebret, David Grangier and Michael Auli |
| Year | 2016 |
| URL | https://arxiv.org/abs/1603.07771 |

Lebret et al. introduce a neural text generation method that is able to generate Wikipedia-like 
biography sentences on the basis of the information present in a Wikipedia infobox. Their model
works like a language model that is conditioned on several types of input: 

- Like any language model, it is conditioned on the sequence of words preceding the current word.
- Furthermore, it is _locally_ conditioned on the information from the table
that has already been taken up in the text. For each relevant word, it takes into account the infobox field
and its position in that field.  
- Finally, it is _globally_ conditioned on all tokens and words in the infobox, irrespective of 
they have already been taken up into the text. This allows the model to produce different 
types of sentences for e.g. sportspeople and politicians. 

All this information is embedded through separate embedding matrices. Their resulting
embeddings are aggregated and fed into a linear layer, followed by a softmax layer that
produces the probabilities for all words in the vocabulary. To deal with the large
vocabularies of Wikipedia articles, the model moreover scores special field tokens
such as _name_1_ or _name_2_, which allow out-of-vocabulary 
words to be copied from the infobox directly.

Comparisons with a Kneser-Ney language model that is trained on biography templates show
that Lebret et al.'s approach is able to achieve a 15-point jump in BLEU, up from 20 to 35.

