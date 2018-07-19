# The Natural Language Decathlon: Multitask Learning as Question Answering

|||
| --- | --- |
| Title | The Natural Language Decathlon: Multitask Learning as Question Answering |
| Authors | Bryan McCann, Nitish Shirish Keskar, Caiming Xiong, Richard Socher |
| Year | 2018 |
| URL | https://arxiv.org/abs/1806.08730 |

Most Deep Learning models are trained to perform just one task. To fix this problem,
McCann et al. introduce the Natural Language Decathlon, a ten-task challenge
including question answering, machine translation, summarization, natural language
inference, sentiment analysis, semantic role labelling, relation extraction,
goal-oriented dialogue, semantic parsing and pronoun resolution. 
Competing systems are scored on each of the ten tasks, and receive a total
score out of 1,000 that is the sum of their individual task scores. There is a
leaderboard on [Github](https://github.com/salesforce/decaNLP).

One way to train a model that is able to perform all ten tasks is to cast
them as question answering. In question answering, the machine is given a 
question and a context, and has to produce an answer. For tasks that similarly take two different inputs, such as
entailment, this means one input (for entailment: the hypothesis) becomes 
the question and the other (for entailment: the premise) becomes the context. For
tasks that take just one input, such as machine translation or summarization, this input becomes
the context, while the question (such as "What is the summary?") merely serves
to identify the task. 

To perform this generic QA challenge, McCann et al. present a multitask 
question answering network (MQAN). It has an encoder based on dual co-attention
and self-attention, and a multi-pointer-generator decoder. This decoder can choose 
to point to the question, to the context or to generate from the vocabulary. This
MQAN obtains a decaScore of 562.7, at least when a specific training strategy
is followed: in a first phase the network is trained on SQuAD, before it is
trained on all tasks jointly. Giving SQuAD this special treatment is motivated
by the question-answering nature of all tasks in the set.
