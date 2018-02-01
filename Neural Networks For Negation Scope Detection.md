# Neural Networks For Negation Scope Detection

|||
| --- | --- |
| Title | Neural Networks For Negation Scope Detection |
| Authors | Federico Fancellu, Adam Lopez, Bonnie Webber |
| Year | 2016 |
| URL | http://www.aclweb.org/anthology/P16-1047 |

In negation scope detection, the goal is to identify the words in a sentence
that fall under the scope of a negation, e.g., *He was* __not__ *driving the 
car* and she left to go home. Fancellu et al. demonstrate that a bidirectional
LSTM without hand-crafted features is competitive with more complex 
systems that rely on heuristics or rules. It even outperforms them when the test data is from the same domain
as the training data.

The LSTM takes as input the tokens in the sentence together with a sentence-length
vector that identifies the negation cue. Both inputs
are embedded into 50-dimensional embeddings, with the embedding matrix for the 
cue input having just two embeddings: *cue* and *notcue*. Pre-trained word
embeddings improve the performance of the system, as does adding universal part-of-speech
information (which is embedded in the same way as the token and cue input).

It is worth noting that the system is evaluated on the shared task of *SEM2012, which has a
small training set of only 848 sentences. An error analysis shows that incorrect decisions are
mainly related to the syntactic structure of the sentence, which is not directly
modelled. 
