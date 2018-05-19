# Universal Language Model Fine-tuning for Text Classification

|||
| --- | --- |
| Title | Universal Language Model Fine-tuning for Text Classification |
| Authors | Jeremy Howard, Sebastian Ruder |
| Year | 2018 |
| URL | https://arxiv.org/abs/1801.06146 |


In most NLP practical approaches, transfer learning is restricted to the embedding layer. Howard
and Ruder show that, like models in Computer Vision, NLP models can also benefit from transfer
learning beyond the embedding layer. They identify language modelling as an ideal source task
that captures many relevant aspects of language and call their method Universal Language Model
Fine-tuning (ULMFiT). ULMFit consists of three steps: 

1. the language model is trained on a general-domain corpus such as Wikipedia,
2. the language model is fine-tuned on target task data,
3. the language model is turned into a classifier by adding two linear blocks and tuning their
parameters on the target data.

A combination of training tricks makes this process extremely effective: 

- _discriminative fine-tuning_: when the language model is fine-tuned, each layer is tuned with 
different learning rates. As deeper layers gradually contain more task-specific information, 
 learning rate should grow with layer depth.
- _slanted triangular training rates_: first the learning rates are linearly increased (quickly),
then they are linearly decayed (slowly).
- _concat pooling_: in the classifier, the hidden state at the last time step 
is concatenated with the max-pooled
and the mean-pooled representation of the other hidden states. This is done because relevant
information may occur anywhere in the document. 
- _gradual unfreezing_: to avoid catastrophic forgetting in the third step, not all layers
are fine-tuned at once. First only the last layer is fine-tuned, and then the other layers
are "unfrozen" and added to the fine-tuning process one by one.

Starting from Merity's (2017) state-of-the-art AWD-LSTM language model, Howard and Ruder
obtain state-of-the-art performance and impressive error reductions on six text classification
tasks. Moreover, they are able to obtain the performance of competing models with far fewer
labelled training examples. 

The model and code are available at [http://nlp.fast.ai/ulmfit](http://nlp.fast.ai/ulmfit).