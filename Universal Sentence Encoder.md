# Universal Sentence Encoder

|||
| --- | --- |
| Title | Universal Sentence Encoder |
| Authors | Daniel Cer, Yinfei Yang, Sheng-yi Kong, Nan Hua, Nicole Limtiaco, Rhomni St. John, Noah Constant, Mario Guajardo-Cespedes, Steve Yuan, Chris Tar, Yun-Hsuan Sung, Brian Strope, Ray Kurzweil |
| Year | 2018 |
| URL | https://arxiv.org/abs/1803.11175 |

Google has released two Tensorflow models for encoding sentences into a fixed-size embedding:

- a Transformer model that takes the element-wise sum of the context-aware word representations
produced by the encoding subgraph of a Transformer model.
- a Deep Averaging Network where input embeddings 
for words and bigrams are averaged together and passed through a feed-forward deep neural network.

The transformer model usually gives better performance, but is more compute- and memory-intensive,
scaling quadratically with sentence length. Both models have been trained on a 
combination of unsupervised data (in a skip-thought-like task)
and supervised data (the SNLI corpus). An evaluation on several types of tasks (sentiment classification, 
question classification, textual similarity, etc.) shows the resulting sentence embeddings
are able to improve task-specific models through transfer learning, 
particularly when little data is available. The best 
performance is achieved when sentence and word level transfer (word2vec embeddings) is combined.

The universal sentence encodings are available in [Tensorflow Hub](https://www.tensorflow.org/hub/modules/google/universal-sentence-encoder/1).