# Kaggle-US-Phrase-Matching
https://www.kaggle.com/competitions/us-patent-phrase-to-phrase-matching/overview/timeline
## Data Description
In this dataset, you are presented pairs of phrases (an anchor and a target phrase) and asked to rate how similar they are on a scale from 0 (not at all similar) to 1 (identical in meaning). This challenge differs from a standard semantic similarity task in that similarity has been scored here within a patent's context, specifically its CPC classification (version 2021.05), which indicates the subject to which the patent relates. For example, while the phrases "bird" and "Cape Cod" may have low semantic similarity in normal language, the likeness of their meaning is much closer if considered in the context of "house".

This is a code competition, in which you will submit code that will be run against an unseen test set. The unseen test set contains approximately 12k pairs of phrases. A small public test set has been provided for testing purposes, but is not used in scoring.

Information on the meaning of CPC codes may be found on the USPTO website. The CPC version 2021.05 can be found on the CPC archive website.

## Score meanings
The scores are in the 0-1 range with increments of 0.25 with the following meanings:

+ 1.0 - Very close match. This is typically an exact match except possibly for differences in conjugation, quantity (e.g. singular vs. plural), and addition or removal of stopwords (e.g. “the”, “and”, “or”).
+ 0.75 - Close synonym, e.g. “mobile phone” vs. “cellphone”. This also includes abbreviations, e.g. "TCP" -> "transmission control protocol".
+ 0.5 - Synonyms which don’t have the same meaning (same function, same properties). This includes broad-narrow (hyponym) and narrow-broad (hypernym) matches.
+ 0.25 - Somewhat related, e.g. the two phrases are in the same high level domain but are not synonyms. This also includes antonyms.
+ 0.0 - Unrelated.

## Files
+ train.csv - the training set, containing phrases, contexts, and their similarity scores
+ test.csv - the test set set, identical in structure to the training set but without the score
+ sample_submission.csv - a sample submission file in the correct format

## Columns
+ id - a unique identifier for a pair of phrases
+ anchor - the first phrase
+ target - the second phrase
+ context - the CPC classification (version 2021.05), which indicates the subject within which the similarity is to be scored
+ score - the similarity. This is sourced from a combination of one or more manual expert ratings.

# References
SBERT:
+ https://zhuanlan.zhihu.com/p/417287003
+ https://www.cnblogs.com/gczr/p/12874409.html

BERT:
+ https://zhuanlan.zhihu.com/p/136496457

BERT model:
+ https://huggingface.co/models
+ (bert-base-uncased) https://huggingface.co/bert-base-uncased
+ (bert-large-uncased) https://huggingface.co/bert-large-uncased
