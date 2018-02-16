# Pointer Networks

|||
| --- | --- |
| Title | Pointer Networks |
| Authors | Oriol Vinyals, Meire Fortunato, Navdeep Jaitly |
| Year | 2015 |
| URL | https://arxiv.org/abs/1506.03134 |

"Traditional" sequence-to-sequence models cannot work with variable-sized
vocabularies. In typical encoder-decoder architectures, with or without
attention, input and output vocabularies are fixed before the models are 
trained. Vinyals et al. introduce a new neural architecture that works
with variable-sized vocubularies by using attention as a pointer to
select a member of the input sequence as the output. 

In other words, where the typical attention mechanism propagates 
weighted contextual information from the encoder to the decoder,
pointer nets use the attention probabilities directly as the output distribution 
over the dictionary of inputs. Vinyals et al. show this neural architecture
can learn solutions to well-known combinatorial optimization problems, such as
the travelling salesman problem. 

In NLP, pointer networks can be useful in settings where the desired output
tokens are always present in the input (like in question answering), or
where this is potentially the case (like with proper nouns that are not present
in the fixed-size vocabulary of MT models). 
