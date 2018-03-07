# Neural Text Generation from Structured Data with Application to the Biography Domain

|||
| --- | --- |
| Title | Learning to generate one-sentence biographies from Wikidata |
| Authors | Andrew Chisholm, Will Radford, Ben Hachey |
| Year | 2017 |
| URL | https://aclweb.org/anthology/E17-1060 |

Chisholm et al. 2017 present a system that generates a one-sentence biography
on the basis of Wikidata facts. The backbone is a sequence-to-sequence
model that takes as input a flat string representation of structured data 
from Wikidata, such as "TITLE mathias tuomi SEX OR GENDER male DATE OF BIRTH 1985-09-03",
where the slots are ordered by frequency. Its encoder and decoder are both
3-layer GRUs, with tied embeddings, and an attention mechanism to focus
generation on specific facts. 

Interestingly, Chisholm et al. extend this encoder-decoder architecture to an
autoencoder, where a second encoder-decoder component tries to regenerate
the Wikidata facts on the basis of the generated sentence. In this way, the system
learns to generate only facts it finds in the Wikipedia input. Experiments show 
this autoencoder setup drastically improves the output of the system beyond
the capabilities of a single encoder-decoder architecture. Its BLEU score
with Wikipedia biography sentences is .41, and its output is preferred 40% 
of the time to the Wikipedia alternative by human judges.

The code and data from this paper can be found on [https://
github.com/andychisholm/mimo](Github).