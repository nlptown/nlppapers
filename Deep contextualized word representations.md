# Deep contextualized word representations

|||
| --- | --- |
| Title | Deep contextualized word representations |
| Authors | Matthew E. Peters, Mark Neumann, Mohit Iyyer, Matt Gardner, Christopher Clark, Kenton Lee, Luke Zettlemoyer |
| Year | 2018 |
| URL | https://arxiv.org/abs/1802.05365 |


Many NLP models rely on word embeddings to achieve optimal performance. Most
use context-insensitive embeddings such as GloVe or word2vec, despite the fact
word meaning can vary considerably between contexts. ELMo fixes this problem 
by assigning to each token a representation that is a function of the entire input sentence.

Embeddings from Language Models (ELMo) gets its name from the fact that its
word representations are derived from a 2-layer bidirectional LSTM language model. 
It distinguishes itself 
from previous approaches in that it combines all of the internal layers of the
language model and lets the downstream model learn weights for each layer.
This allows the model to select the type of information that is most
useful for its particular task.
Indeed, experimental results show that lower layers are more sensitive to syntactic
information (they are more useful for PoS tagging), while higher layers encode more
 semantic information (they are better at word sense disambiguation). 

Typically, ELMo is added to a model by freezing the BiLM weights and using as model input
a concatenation of the BiLM vectors with a context-insensitive (convolutional character-based)
token representation. Sometimes concatenating the ELMo vector with the output of the task RNN 
improves performance further. Often it is beneficial to fine-tune the BiLM
on domain-specific data. The upgraded models achieve very impressive results across
a wide range of tasks, with
relative error reductions between 5.8% (for SNLI) to 24.9% (for SQuAD).

The ELMo embedder is available with [AllenNLP](https://github.com/allenai/allennlp/blob/master/tutorials/how_to/elmo.md).
