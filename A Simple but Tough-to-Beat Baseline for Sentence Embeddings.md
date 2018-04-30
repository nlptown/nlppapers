# A Simple but Tough-to-Beat Baseline for Sentence Embeddings

|||
| --- | --- |
| Title | A Simple but Tough-to-Beat Baseline for Sentence Embeddings |
| Authors | Sanjeev Arora, Yingyu Liang, Tengyu Ma |
| Year | 2017 |
| URL | https://openreview.net/pdf?id=SyK00v5xx |

Arora et al. introduce a simple two-step baseline for computing sentence embeddings from the 
word embeddings of the tokens in the sentence: 

1. Smooth inverse frequency: compute the weighted average of the word embeddings in the sentence. 
Every word embedding is 
weighted by `a/(a + p(w))`, where `a` is a parameter and `p(w)` the estimated frequency
of the word. The best performance is obtained with `a` between `10^-3` and `10^-4`. `P(w)` can
be estimated on a variety of corpora (such as Wikipedia), with the precise choice having
little effect on the results.

2. Common component removal: compute the principal component of the resulting vectors
for a set of sentences and subtract from them their projections on this first principal component.

This two-step method is motivated by a random walk model of discourse, where the probability
of a word being generated is proportional to the inner product between a discourse vector
and the time-invariant word vector. The sentence embedding is then an MAP estimate of the
discourse vector given the words. In addition, the authors show their weighting scheme
is similar to the subsampling probabilities in word2vec.

An evaluation across a wide range of sentence similarity tasks shows this method improves upon 
(unweighted) average word embeddings by a large margin, and can even outperform supervised
models such as LSTMs. The sentence embeddings can also be used with good results as features
for downstream supervised tasks (such as entailment or sentiment classification), but its
advantage is smaller there.