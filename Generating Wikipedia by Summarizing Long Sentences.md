# Generating Wikipedia by Summarizing Long Sentences

|||
| --- | --- |
| Title | Generating Wikipedia by Summarizing Long Sentences |
| Authors | Peter J. Liu, Mohammad Saleh, Etienne Pot, Ben Goodrich, Ryan Sepassi, Lukasz Kaiser, Noam Shazeer |
| Year | 2018 |
| URL | https://arxiv.org/pdf/1801.10198.pdf |

This paper addresses the task of generating medium-length text from a wide
variety of input texts: the goal is to generate the lead of a Wikipedia article
on the basis of the texts linked in the references and the ten highest ranked 
Google search results, using the title as a query. 

The summarization process consists of 2 steps: 

- an _extractive_ summarization step that identifies the most relevant paragraphs
in the input texts, and
- an _abstractive_ summarization step that generates a new text on the basis
of these most relevant paragraphs.

The extractive summarization step relies on traditional techniques such as
tf-idf scores for the title query with respect to the paragraph; the abstractive
summarization step makes use of neural sequence-to-sequence models. The best results are
obtained with a transformer decoder (without an encoder) with memory-compressed attention: through
 5 consecutive layers, attention is alternately performed in sequential blocks of 256 tokens independently, and compressed using 
 convolutional kernels of size 3 with stride 3. This transformer architecture is 
 tailored specifically for long sequences, and clearly outperforms more traditional
 sequence-to-sequence architectures such as an LSTM encoder-decoder on this task.
 

