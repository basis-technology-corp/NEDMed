# NEDMed Dataset

Copyright (c) 2022 Basis Technology, Inc.

This dataset has been released alongside "Improving Few-Shot Domain Transfer for 
Named Entity Disambiguation with Pattern Exploitation" by BasisTech.

The dataset is split into NEDMed-train and NEDMed-dev. Each file contains a single JSON document,
which has been annotated with entities. The `documentMetadata` field contains
various pieces of metadata relating to the source document and/or the annotators/adjudicators.

Within the `nedmed-train` and `nedmed-dev` folders, there are two subfolders:
- `raw` contains the annotated data (containing entities and their Wikidata QIDs), without any redactions
- `with-candidates` contains the annotated data along with the list of candidates used in "Improving Few-Shot Domain Transfer for Named Entity Disambiguation with Pattern Exploitation". This is intended for the evaluation of disambiguation-only models.

Here is an example of an entity:
```
        {
          "mentions": [
            {
              "startOffset": 85,
              "endOffset": 101
            }
          ],
          "type": "LOC",
          "entityId": "Q16572",
          "candidates": [
            {
              "enwikiId": "en_12537",
              "enwikiPage": "https://en.wikipedia.org/?curid=12537",
              "qid": "Q16572",
              "title": "Guangzhou"
            }
          ],
          "goldIdx": 0
        },
```
`mentions[0]` indicates the location in the document's `data` field of the mention.

`candidates` and `goldIdx` are only found inside of the `with-candidates` subfolders. Each candidate
contains the English Wikipedia page ID (as of January 2022) and Wikidata QID. The `goldIdx` field indicates
which entry in the candidate list is the zero-indexed correct answer (which can also be deduced from the 
QID in the `entityId` field), or -1 if the candidate is not in the list.

For license information, please see LICENSE.

# Citing
```
@inproceedings{blair-bar-2022-improving-few-shot,
    title = "Improving Few-Shot Domain Transfer for Named Entity Disambiguation with Pattern Exploitation",
    editor = "Blair, Philip  and
      Bar, Kfir",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2022",
    month = dec,
    year = "2022",
    address = "Abu Dhabi, United Arab Emirates",
    publisher = "Association for Computational Linguistics",
}
```
