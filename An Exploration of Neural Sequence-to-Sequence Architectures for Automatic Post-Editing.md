# An Exploration of Neural Sequence-to-Sequence Architectures for Automatic Post-Editing

|||
| --- | --- |
| Title | An Exploration of Neural Sequence-to-Sequence Architectures for Automatic Post-Editing |
| Authors | Marcin Junczys-Dowmunt, Roman Grundkiewicz |
| Year | 2017 |
| URL | https://arxiv.org/abs/1706.04138 |


Automatic Post-Editing (APE) is the task of automatically correcting Machine
Translation output. Junczys-Dowmunt and Grundkiewicz investigate a variety of
attention-based architectures for this task. All these architectures share an 
encoder-decoder setup, where the encoder is a bidirectional GRU, and the 
decoder is a two-layer GRU with attention. The difference between them lies
in the concrete implementation of attention: 

- Hard monotonic attention, where the model looks at one encoder state at a time, 
starting from the left and ending at the right. See [here](https://github.com/nlptown/nlppapers/blob/master/Morphological%20Inflection%20Generation%20with%20Hard%20Monotonic%20Attention.md).
- A combination of hard and soft attention, where the attention-based decoder is presented
with a concatenation of the embedding of the previous symbol and the hard-attended
encoder output.
- Soft dual attention, where two separate encoders encode the MT output and the MT source. 
The decoder GRU attends to the output of both encoders.
- Hard attention with soft dual attention, where the previous model is extended with 
hard attention. 

Junczys-Dowmunt and Grundkiewicz evaluate these four models on the data of the WMT-2016
automatic post-editing task. Hard attention performs worst overall, but it has the
advantage of remaining more faithful to the original MT output. The dual
attention models emerge as the clear winners. 

Implementations of all the models are available in the [Marian toolkit](https://marian-nmt.github.io/).