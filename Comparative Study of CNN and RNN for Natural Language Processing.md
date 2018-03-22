# Comparative Study of CNN and RNN for Natural Language Processing

|||
| --- | --- |
| Title | Comparative Study of CNN and RNN for Natural Language Processing |
| Authors | Wenpeng Yin, Katharina Kann, Mo Yu, Hinrich Schütze |
| Year | 2017 |
| URL | https://arxiv.org/abs/1702.01923 |

Yin et al. compare the performance of basic convolutional and recurrent neural networks
(LSTMs and GRUs) on a wide range of NLP tasks. Their results give a mixed picture: GRUs 
perform best on the text classification, textual entailment and path query answering tasks,
BiLSTMs give the best performance on part-of-speech tagging, and CNNs are best at 
answer selection and question relation matching. 

A qualitative analysis shows that GRUs shine when the full sequence or long-range
semantic dependencies are needed to predict the correct label; CNNs are particularly
good at predicting output that is determined by local keyphrases. This is also reflected
in the finding that GRUs outperform CNNs particularly on long sentences. 

Finally, an analysis of hyperparameter settings also indicates that the performance of
individual models varies smoothly with changing learning rates, while even small
variations in hidden sizes and batch sizes can cause large oscillations. 
