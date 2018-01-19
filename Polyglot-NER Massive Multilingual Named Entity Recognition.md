# Polyglot-NER Massive Multilingual Named Entity Recognition

|||
| --- | --- |
| Title | Polyglot-NER Massive Multilingual Named Entity Recognition |
| Authors | Rami Al-Rfou, Vivek Kulkarni, Bryan Perozzi and Steven Skiena |
| Year | 2014 |
| URL | https://arxiv.org/abs/1410.3791 |

Al-Rfou et al. describe how they built a Named Entity Recognition system for 40 languages. They model NER as a word-level classification problem with as only features the word embeddings in a fixed context window around the target word. To train their models, they collected data from Wikipedia and labelled it automatically:  

- They labelled every internal link in a Wikipedia article with an entity label if the link referred to a Wikipedia page that corresponds to a Freebase entity (location, organization or person).
- Because not all entity mentions are linked in Wikipedia, training a model on this initial data results in very poor performance (F1<10%). However, the training data can be manipulated to give state-of-the-art performance: 
    - Oversampling the entities so that around 50% of the training data refers to an entity leads to an increase in F-score of at least 40% for all languages considered. 
    -  Extending the entity annotations to all words that appear in a labelled entity mention within the same article or the title of the current article, makes sure that also single-term mentions (instead of full combinations of first name and last name) and self-referential links are labelled. This leads to another jump in performance, particularly for person entities.