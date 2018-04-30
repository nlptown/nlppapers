# Supervised Learning of Universal Sentence Representations from Natural Language Inference Data

|||
| --- | --- |
| Title | Supervised Learning of Universal Sentence Representations from Natural Language Inference Data |
| Authors | Alexis Conneau, Douwe Kiela, Holger Schwenk, Loic Barrault, Antoine Bordes |
| Year | 2017 |
| URL | https://arxiv.org/abs/1705.02364 |

While many NLP systems rely on pre-trained word embeddings, the use of pre-trained sentence
embeddings is much less widespread. In this paper, Conneau et al. develop and train a
universal sentence encoder whose sentence representations prove useful in many transfer
learning settings: 

- As training data Conneau et al. use the SNLI dataset, a set of 570k English sentence pairs that 
have all been labelled with one of three categories: entailment, contradiction or neutral. 
They argue this natural language inference data is ideal for learning 
sentence representations that capture universal features. 

- Among alternative sentence encoder architectures, such as traditional LSTMs and GRUs,
self-attentive networks and hierarchical ConvNets, they find a BiLSTM with max pooling
performs best on a wide range of tasks. The transfer test results moreover show the
representations produced by this encoder help the receiving models achieve state-of-the-art
results in many downstream tasks, such as sentence classification, semantic 
relatedness and paraphrase detection. 

The InferSent encoder is available on [Github](https://github.com/facebookresearch/InferSent).