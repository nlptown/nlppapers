# Morphological Inflection Generation with Hard Monotonic Attention

|||
| --- | --- |
| Title | Morphological Inflection Generation with Hard Monotonic Attention |
| Authors | Roee Aharoni, Yoav Goldberg |
| Year | 2016 |
| URL | https://arxiv.org/abs/1611.01487 |

In morphological inflection generation, the task is to generate a target word 
(e.g. "hardest"), given a source word (e.g. "hard") and a set of morphosyntactic
attributes (e.g. adjective, masculine, superlative). This task can alleviate
data sparsity in challenges such as machine translation. 

Aharoni and Goldberg present a model for this task that uses a character-based 
encoder-decoder architecture with a hard attention mechanism.
In contrast to the more popular, soft attention, here every decoding
step attends to a single input state. At each step, the decoder is fed a concatenation
of the current attended input, a set of embeddings for the morphosyntactic attributes
and the embedding of the previous output symbol. Possible output symbols are
the vocabulary of characters and the STEP action, which indicates the attention of the
decoder moves to the next character in the input. 

Unlike other work in sequence transduction, Aharoni and Goldberg have found that 
it is worthwile to learn hard alignments in advance and train the model on 
explicitly aligned sequences. Their experiments on three data sets show that the
hard attention model is at least competitive with other models and clearly 
outperforms them when little data is available.