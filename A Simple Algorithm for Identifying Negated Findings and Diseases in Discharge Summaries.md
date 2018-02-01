# A Simple Algorithm for Identifying Negated Findings and Diseases in Discharge Summaries
|||
| --- | --- |
| Title | A Simple Algorithm for Identifying Negated Findings and Diseases in Discharge Summaries |
| Authors | Wendy W. Chapman, Will Bridewell, Paul Hanbury, Gregory F. Cooper, Bruce G. Buchanan*, |
| Year | 2001 |
| URL | https://www.ncbi.nlm.nih.gov/pubmed/12123149 |

Chapman et al. present NegEx, a simple rule-based algorithm that identifies when clinical findings
and diseases in medical texts are negated. It relies on a set of 35 negation phrases: 
normal negation phrases, which indicate negation (such as "absence of"), and "pseudo-negation" phrases, which appear to indicate
negation, but do not (such as "not rule out"). 

- A finding or disease is assumed to be
negated when it precedes or follows a normal negation phrase, with up to five tokens (not counting
punctuation) separating them. 
- If a finding or disease occurs several times in a sentence,
it is assumed to be negated when at least one of its occurrences is negated.

Despite its simplicity, NegEx clearly outperforms 
a baseline that looks for negation words and negates
all findings and diseases that come after that negation word in the same sentence.
Still, it is inherently limited because it applies simple string matching and
does not analyze the linguistic structure of the sentence.
