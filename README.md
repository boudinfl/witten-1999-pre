# Preprocessed CSTR keyphrase extraction benchmark dataset

This dataset was introduced in:

 - **KEA: Practical automatic keyphrase extraction.**
   Witten, I. H., Paynter, G. W., Frank, E., Gutwin, C., & Nevill-Manning, C. G.
   *In Proceedings of the fourth ACM conference on Digital libraries.*
   p. 254-255. ACM.

The dataset is split into four directories:

  * `references`: reference keyphrases for evaluation
  * `test`: test set
  * `train`: training set
  * `src`: scripts and archive from which the dataset is built

Each input file is processed using the Stanford CoreNLP suite v3.6.0.
We use the default parameters and perform tokenization, sentence splitting and
Part-Of-Speech (POS) tagging. Files are in XML format.

We original raw text dataset can be retreived from this [link](witten-1999).

Reference keyphrases are in json format and named according to the following
rules:

    [test|train].author.[stem]?.json

author-provided (stemmed or not) reference keyphrases for test or train splits.

Stemming (if applied), is performed with nltk Porter algorithm (English).

Below is a toy example of reference file:

    {
        "doc-1": [
            [
                "target detect"
            ],
            [
                "number of sensor",
                "sensor number"
            ]
        ],
        ...
    }

[witten-1999]: http://www.cs.waikato.ac.nz/~eibe/kea_data/CSTR.tar.gz