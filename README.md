---
license: cc-by-4.0
language:
- fr
- en
- de
- es
pretty_name: Qulture Multilingual General Knowledge Question Dataset
tags:
- general-knowledge
- quiz
- education
- multilingual
- open-data
task_categories:
- question-answering
configs:
- config_name: default
  data_files:
  - split: train
    path: qulture-general-knowledge-questions.csv
---

# Qulture Multilingual General Knowledge Question Dataset

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22108528.svg)](https://doi.org/10.5281/zenodo.22108528)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

An open dataset containing 16 families of general knowledge questions in French, English, German and Spanish, for a total of 64 records.

Each record includes a question, four answer choices, correctness indicators, the correct answer, an explanation, stable identifiers, translation relationships and separate source metadata. The dataset is intended for education, research, cultural projects, multilingual experiments and quiz applications.

## Files

- `qulture-general-knowledge-questions.csv` — tabular distribution used by the dataset viewer;
- `qulture-general-knowledge-questions.json` — canonical structured distribution with dataset-level metadata;
- `CITATION.cff` — citation metadata;
- `LICENSE.md` — CC BY 4.0 attribution and reuse terms;
- `CHANGELOG.md` — release history.

## Dataset structure

The 64 records represent 16 question families × 4 languages:

- French (`fr`)
- English (`en`)
- German (`de`)
- Spanish (`es`)

Important fields include:

| Field | Description |
| --- | --- |
| `family_id` | Stable identifier shared by translated versions |
| `id` | Qulture record identifier |
| `language` | ISO language code |
| `question` | Question text |
| `options` | Four answer choices |
| `correct_indicators` | Boolean correctness values aligned with the choices |
| `correct_answer` | Correct answer text |
| `anecdote` | Explanation and additional context |
| `translations` | IDs of the related language versions |
| `source` | Source URL, label and verification date |

## Quick start

```python
from datasets import load_dataset

dataset = load_dataset("csv", data_files="qulture-general-knowledge-questions.csv")
print(dataset["train"][0])
```

The CSV fields containing arrays or objects are JSON-encoded strings. The JSON distribution preserves their native nested structure.

## Source and documentation

- English documentation: https://www.qulture-app.com/en/open-data/
- French documentation: https://www.qulture-app.com/open-data/
- Permanent release: https://doi.org/10.5281/zenodo.22108528
- French national open-data catalogue: https://www.data.gouv.fr/datasets/corpus-multilingue-de-questions-de-culture-generale-qulture
- Educational resource: https://oercommons.org/courses/qulture-multilingual-general-knowledge-question-dataset

## License and attribution

The dataset is released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

Suggested attribution:

> Qulture (2026). *Qulture Multilingual General Knowledge Question Dataset*, version 1.0.0. Zenodo. https://doi.org/10.5281/zenodo.22108528

Individual source URLs remain included as provenance metadata. Reusers should preserve them when practical.

## Limitations

- This first edition contains 64 records and is not intended to be an exhaustive general knowledge benchmark.
- Cultural context and question difficulty may vary between topics and languages.
- Source pages can change after the verification date stored in each record.
- Image fields are identifiers or references; image reuse rights are not granted by the dataset license unless explicitly stated by the original rights holder.

## Version

Edition 1 — version 1.0.0 — published 2026-08-23.
