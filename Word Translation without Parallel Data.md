# Word Translation without Parallel Data

|||
| ---- | ---- |
| Title | Word Translation Without Parallel Data |
| Authors | Alexis Conneau, Guillaume Lample, Marc'Aurelio Ranzato, Ludovic Denoyer, Hervé Jégou |
| Year | 2017 |
| URL | https://arxiv.org/abs/1710.04087 |

Word embeddings that have been trained on monolingual corpora do not allow
cross-lingual comparisons. While there are methods to align two monolingual
embedding spaces, these generally need bilingual dictionaries to perform well. 
Conneau et al. introduce a fully unsupervised way to learn a good mapping
between two embedding spaces that even outperforms supervised competitors. 

Conneau et al.'s method starts with an adversarial training phase, where the discriminator is trained
to identify mapped source embedding and original target embeddings as such, while
the mapping is trained to trick the discriminator into thinking a mapped source
embedding is actually a true target embedding and vice versa. After this first 
step, they identify frequent cross-lingual word pairs that are mutual nearest
neighbours in the mapped space. These word pairs are then used as a bilingual
dictionary to refine the mapping using the Procrustes solution applied by 
Artetxe et al. (2017). This procedure can be repeated several times to improve the 
mapping further.

To compute cross-lingual similarity, Conneau et al. use a scaled
version of the cosine metric. This similarity measure mitigates the hubness problem 
(where points in high-dimensional spaces tend to be neighbours of many other points)
by penalizing words whose embeddings are similar to many different cross-lingual
neighbours. To select the best mapping without relying on parallel data, they
simply choose the mapping where the translations suggested by their metric have
the highest similarity value on average.
 
Conneau et al. show their method outperforms most competitors on word translation,
cross-lingual semantic word similarity and sentence translation retrieval.
The relevant code has been released in the MUSE library at 
[https://github.com/facebookresearch/MUSE](https://github.com/facebookresearch/MUSE).
