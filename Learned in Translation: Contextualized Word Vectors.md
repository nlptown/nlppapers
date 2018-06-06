# Learned in Translation: Contextualized Word Vectors

|||
| --- | --- |
| Title | Learned in Translation: Contextualized Word Vectors |
| Authors | Bryan McCann, James Bradbury, Caiming Xiong, Richard Socher |
| Year | 2017 |
| URL | https://arxiv.org/abs/1708.00107 |

While computer vision models typically benefit from transfer learning at multiple
layers, NLP models tend to make use of pre-trained uncontextualized word vectors only. 
McCann et al. show that contextualizing these word vectors has a positive effect on the
performance in many tasks, including text classification, entailment and question answering.

CoVe (Contextualized Vectors) achieves this contextualization by training an LSTM encoder as part of a Machine 
Translation model and using the trained encoder to process the input sentences for another
task. The encoder output for each word is then concatenated with the GloVe embedding
for that word, and the sequence of the resulting vectors is sent to the classification model, a biattentive classification network. 
This improves the results on all tasks in the paper with a few percentage points. The larger
the MT training corpus, the larger this improvement becomes. The best results are achieved
by combining CoVe with GloVe and character n-gram embeddings.

