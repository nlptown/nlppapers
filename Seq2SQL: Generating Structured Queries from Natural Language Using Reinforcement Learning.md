# Seq2SQL: Generating Structured Queries from Natural Language Using Reinforcement Learning

|||
| --- | --- |
| Title | Seq2SQL: Generating Structured Queries from Natural Language Using Reinforcement Learning |
| Authors | Victor Zhong, Caiming Xiong, Richard Socher
| Year | 2017 |
| URL | https://arxiv.org/abs/1709.00103 |

Relational databases contain a wealth of information, but many potential users lack the SQL skills 
to consult them. Zhong et al. investigate a neural-network model that translates a natural
language question into a SQL query that returns the correct answer from a relational database. 

Seq2SQL takes as input a natural language question and table schema. The encoder reads the concatenation of the
embedded column names, the natural language question, and the required SQL vocabulary (e.g. SELECT,
COUNT). The model then produces an SQL query in three steps:

- The _aggregation classifier_ decides what aggregation operation should take place.
It computes an attention distribution over the input encodings in 
the question and then applies a multi-layer perceptron to classify the question by 
aggregation operation (such as COUNT, MIN, MAX or NULL).

- The _SELECT column pointer_ determines what table column contains the relevant information.
It reads the embedded column names and the question. It 
computes another attention-weighted representation of the question, combines it with
 the column embeddings, and feeds it to a multi-layer perceptron that
assigns a score to each column. 
 
- The _WHERE clause decoder_ is a pointer decoder that generates
the WHERE clause of the query token by token. Because the order of the conditions
is free, it is trained using reinforcement learning, where the reward depends
on whether the produced query is valid and returns the correct result.

Zhong et al. also release WikiSQL, a dataset of around 80.000 hand-annotated
examples of questions and their corresponding SQL queries. On this dataset, their
model dramatically outperforms all alternative approaches, with a test accuracy
of 59.4%.