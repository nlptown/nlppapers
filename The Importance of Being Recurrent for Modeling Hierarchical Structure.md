# The Importance of Being Recurrent for Modeling Hierarchical Structure

|||
| --- | --- |
| Title | The Importance of Being Recurrent for Modeling Hierarchical Structure |
| Authors | Ke Tran, Arianna Bisazza, Christof Monz |
| Year | 2018 |
| URL | https://arxiv.org/abs/1803.03585 |

Tran et al. investigate whether recurrent and non-recurrent neural network architectures
are equally successful at modelling hierarchical structure. The recurrent architecture 
under investigation is an LSTM; the non-recurrent one is a Transformer network, which has 
full access to the sequence history through a self-attention mechanism. 

Tran et al. test these
architectures on two tasks: subject-verb agreement, where the goal is to predict the number
of the verb in a sentence, and logical inference, where the 
goal is to predict the logical relationship between a premise and hypothesis. 

On both tasks, the LSTM outperforms the Transformer network. In particular, LSTMs appear
more robust to the presence of misleading features and generalize better to longer sequences.
Therefore, when hierarchical structure matters, recurrent networks should be preferred to
non-recurrent ones.