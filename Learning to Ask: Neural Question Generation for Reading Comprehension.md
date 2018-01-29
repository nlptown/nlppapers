# Learning to Ask: Neural Question Generation for Reading Comprehension

|||
| --- | --- |
| Title | Learning to Ask: Neural Question Generation for Reading Comprehension |
| Authors | Xinya Du, Junru Shao, Claire Cardie |
| Year | 2017 |
| URL | https://arxiv.org/abs/1705.00106 |

Du et al. use an attention-based sequence-to-sequence model to generate questions 
from Wikipedia articles. Traditionally, question generation is tackled with rule-based
models that contain deep linguistic knowledge to transform a sentence to a relevant 
question. Such models typically suffer from low variation in the questions and a lack of fluency. 

Du et al's model takes as input a sentence and optionally, a paragraph. It encodes this
input with a bidirectional LSTM encoder, followed by an attention mechanism and
a decoder that generates a question. This closely resembles 
the seq2seq architecture we also find in machine translation. When
the decoder outputs an UNK token, this is automatically replaced by the token 
in the input sentence with the highest attention score.

Du et al. train and test their model on the SQuAD data set, which consists of human-generated
questions and their corresponding Wikipedia paragraphs. The results show their
neural model with pre-trained word embeddings clearly outperforms all rule-based
approaches. Moreover, a human evaluation of a subset of questions indicates that
the generated questions are much more natural and difficult than those produced by a rule-based
system. Encoding paragraph information was only found to be useful for those
questions that explicitly rely on information present somewhere else in the
paragraph than in the target sentence; on average it brought down performance slightly.
 
