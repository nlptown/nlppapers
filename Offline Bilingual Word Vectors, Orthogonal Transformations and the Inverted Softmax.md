# Offline Bilingual Word Vectors, Orthogonal Transformations and the Inverted Softmax

|||
| --- | --- |
| Title | Offline Bilingual Word Vectors, Orthogonal Transformations and the Inverted Softmax |
| Authors | Samuel L. Smith, David H. P. Turban, Steven Hamblin, Nils Y. Hammerla |
| Year | 2017 |
| URL | https://arxiv.org/abs/1702.03859 |

There are many pre-trained monolingual embeddings available, but very few 
multilingual ones. Nevertheless, it is possible to align pre-trained monolingual
embeddings with a linear transformation trained on bilingual dictionaries.  
Smith et al. show this transformation should be orthogonal. This is true because
the similarities between source and target words should be symmetric, and 
we would like the transformation to be able to map back the target embeddings
into the source embeddings. Because orthogonal transformations are robust to 
noise, they can moreover be trained on artificial dictionaries of identical 
strings shared between two languages.

In addition, Smith et al. introduce the "inverted softmax" for identifying translation 
pairs. This inverted softmax estimates the probability that a candidate
target word translates into the source word rather than the other way around. It
can therefore deal better with "hubs", target words that are nearest neighbours
to many different source words. Combining orthogonal transformations with this
orthogonal softmax increases precision from 34% to 43% on 
English-to-Italian word translation. 

Smith et al. have released their code and their transformation matrices
for 78 FastText embedding matrices at 
[https://github.com/Babylonpartners/fastText_multilingual](https://github.com/Babylonpartners/fastText_multilingual).
