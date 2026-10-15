# Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse

ARI 510 project on sarcasm detection in Turkish–English code-switched online discourse, with an initial focus on fan discussions.

## Overview

This project investigates sarcasm detection in **Turkish–English code-switched online discourse**, particularly conversations involving television series, films, actors, characters, and storylines.

Sarcasm can be challenging to identify because its interpretation often depends on conversational context, tone, irony, emojis, and cultural references. Code-switching introduces an additional challenge because meaning may be expressed across two languages within the same conversation.

The project began with naturally occurring Turkish–English fan discussions collected from Reddit and YouTube. The dataset was subsequently expanded using additional Reddit conversations and synthetically adapted Turkish–English code-switched replies.

The goal of this project is to develop a **human-annotated dataset** and evaluate machine-learning approaches for automatically detecting sarcasm in Turkish–English code-switched text.

## Phase 1: Dataset and Annotation

The first phase of the project focuses on dataset development and validation of the human annotation process.

An initial pilot dataset of **50 parent–reply pairs** was collected from online fan discourse:

- **YouTube:** 28 pairs (56%)
- **Reddit:** 22 pairs (44%)

Following the pilot, the dataset was expanded to **800 parent–reply pairs**:

- **Reddit:** 772 pairs (96.5%)
- **YouTube:** 28 pairs (3.5%)

The expanded dataset includes the initial pilot examples and additional conversational data. Some of the additional replies were synthetically adapted to incorporate Turkish–English code-switching.

Each instance consists of:

1. A **parent comment** providing conversational context.
2. A **reply** serving as the target text for sarcasm annotation.
3. Basic metadata, including the source platform, timestamp, and language-mixing category.

The expanded dataset is available in [`Dataset/unlabeled_data.csv`](Dataset/unlabeled_data.csv).

No sarcasm labels were assigned during data collection or dataset expansion. Labels will be obtained through independent human annotation.

## Dataset Development

The dataset was developed in two stages.

### Pilot Dataset

The initial 50-example pilot dataset was assembled from Reddit and YouTube discussions related to Turkish television series, films, actors, characters, and storylines.

The pilot was used to test the annotation guidelines, annotation interface, and classification task.

### Expanded Dataset

Following the pilot, the dataset was expanded to **800 parent–reply pairs**.

Additional Reddit conversations were incorporated, and Turkish–English code-switching adaptations were created for part of the expanded dataset.

The expanded data therefore includes both collected social-media material and synthetically adapted replies. The platform metadata refers to the source discussion and does not necessarily indicate that the modified bilingual reply appeared verbatim on the original platform.

The expanded dataset also includes broader conversational topics beyond television and fan discourse.

The dataset was checked for structural consistency, duplicate instances, missing fields, and identified language-mixing issues. However, automatic checks do not establish that every synthetically adapted example is fully natural, and annotators may flag unclear or unnatural expressions.

Detailed information is available in [`Dataset/README.md`](Dataset/README.md).

## Annotation Labels

Each reply is classified into one of three categories:

- **Sarcastic (1)** — the reply expresses sarcasm, irony, mock praise, or a meaning that contrasts with its literal wording.
- **Non-sarcastic (0)** — the reply communicates its intended meaning without sarcasm.
- **Ambiguous / Uncertain (U)** — there is insufficient evidence to confidently determine whether the reply is sarcastic.

When **Ambiguous / Uncertain** is selected, annotators also identify the main reason for uncertainty:

- Insufficient conversational context
- Drama/character context needed
- Language/expression unclear
- Tone genuinely ambiguous
- Other

The presence of Turkish expressions, negative sentiment, or emotional language alone is not considered sufficient evidence of sarcasm.

## Annotation Interface

The annotation interface was developed using **Potato**.

Annotators independently:

1. Read the parent comment and reply.
2. Select one sarcasm label.
3. If **Ambiguous / Uncertain** is selected, identify the main reason for uncertainty.
4. Complete the assigned examples without searching online for additional context.

The annotation interface is hosted online for independent annotation:

**Annotation Interface:** https://detecting-sarcasm-in-code-switched.onrender.com

## Internal Pilot

The complete 50-item pilot dataset was internally annotated to test the annotation guidelines and interface.

The internal pilot produced:

- **Sarcastic:** 19
- **Non-sarcastic:** 18
- **Ambiguous / Uncertain:** 13

These internal annotations were used to evaluate the annotation setup and are **not considered final ground-truth labels**.

Final labels will be determined after collecting annotations from multiple annotators, evaluating **inter-annotator agreement**, and reviewing cases with substantial disagreement.

## Expanded Dataset Annotation

The expanded dataset contains **800 unlabeled parent–reply pairs** prepared for independent human annotation.

Annotators will examine the target reply together with its parent comment and assign one of the three sarcasm categories.

After annotation, the project will:

1. Collect and organize annotations from independent annotators.
2. Calculate inter-annotator agreement using Cohen's kappa where applicable.
3. Examine disagreements and ambiguous examples.
4. Review examples flagged for unclear or unnatural language mixing.
5. Establish the final labeled dataset for model development and evaluation.

The expanded dataset is currently unlabeled; no final sarcasm label distribution is reported at this stage.

## Dataset Documentation

Detailed dataset documentation is available in the [`Dataset`](Dataset/) directory:

- [`pilot_data.csv`](Dataset/pilot_data.csv) — initial 50-item pilot dataset
- [`unlabeled_data.csv`](Dataset/unlabeled_data.csv) — expanded 800-item unlabeled dataset
- [`README.md`](Dataset/README.md) — dataset documentation and expansion methodology
- [`Data_Collection_Criteria.md`](Dataset/Data_Collection_Criteria.md) — inclusion and exclusion criteria
- [`LICENSE.md`](Dataset/LICENSE.md) — dataset licensing information

The expanded dataset includes both collected and synthetically adapted examples. The distinction between these sources is documented to support transparent interpretation of the dataset and its limitations.

## Annotation Documentation

Annotation materials are available in the [`Annotation`](Annotation/) directory:

- [`Annotation_Guidelines.md`](Annotation/Guidelines/Annotation_Guidelines.md) — complete annotation guidelines
- [`config.yaml`](Annotation/Interface/config.yaml) — Potato annotation configuration
- [`Dockerfile`](Annotation/Interface/Dockerfile) — deployment configuration
- [`requirements.txt`](Annotation/Interface/requirements.txt) — additional deployment requirements

## Proposal

Project proposal materials are available in the [`Proposal`](Proposal/) directory:

- [`Original_Proposal.pdf`](Proposal/Original_Proposal.pdf) — original project proposal
- [`Updated_Proposal.pdf`](Proposal/Updated_Proposal.pdf) — updated project proposal
- [`Changes_from_Proposal.md`](Proposal/Changes_from_Proposal.md) — summary of changes made after proposal feedback

## Project Workflow

The overall project workflow is:

**Data Collection → Annotation Guidelines → Pilot Dataset → Annotation Interface → Internal Pilot → Dataset Expansion (800 Examples) → Independent Human Annotation → Inter-Annotator Agreement → Disagreement Resolution → Ground-Truth Labels → Modeling and Evaluation**

## Planned Modeling

After completing the annotation and dataset-development stages, the project will evaluate sarcasm classification approaches including:

- **TF-IDF + Logistic Regression** as a baseline
- **Transformer-based models** for contextual sarcasm classification

The models will be evaluated on their ability to identify sarcasm in Turkish–English code-switched text.

The evaluation will consider classification performance and the challenges associated with bilingual language use, conversational context, and ambiguous expressions.

## Dataset Limitations

The following limitations are relevant to the expanded dataset:

- Some code-switched replies were synthetically adapted rather than naturally produced by bilingual social-media users.
- The expanded dataset includes general Reddit conversations beyond the original fan-discourse focus.
- Reddit examples substantially outnumber YouTube examples.
- Some Turkish expressions may be repeated across multiple examples.
- Comment lengths vary considerably.
- Linguistic naturalness and annotation ambiguity require human review.

These limitations will be considered when interpreting annotation agreement and model performance.

## Repository Structure

```text
Detecting-Sarcasm-in-Code-Switched-Turkish-English-Fan-Discourse/
│
├── README.md
│
├── Dataset/
│   ├── pilot_data.csv
│   ├── unlabeled_data.csv
│   ├── Data_Collection_Criteria.md
│   ├── LICENSE.md
│   └── README.md
│
├── Annotation/
│   ├── README.md
│   ├── Guidelines/
│   │   └── Annotation_Guidelines.md
│   └── Interface/
│       ├── config.yaml
│       ├── Dockerfile
│       ├── requirements.txt
│       └── layouts/
│
└── Proposal/
    ├── Original_Proposal.pdf
    ├── Updated_Proposal.pdf
    └── Changes_from_Proposal.md
```

## Current Status

**Phase 1: Dataset Development and Annotation**

- [x] Pilot dataset collected (50 examples)
- [x] Data collection criteria defined
- [x] Annotation guidelines developed
- [x] Potato annotation interface implemented
- [x] Annotation workflow tested
- [x] Internal 50-item pilot completed
- [x] Dataset documentation and licensing prepared
- [x] Dataset expanded to 800 examples
- [x] Expanded unlabeled dataset uploaded to GitHub
- [ ] Independent human annotation of the expanded dataset
- [ ] Inter-annotator agreement analysis
- [ ] Disagreement resolution and ground-truth labels

**Phase 2: Modeling and Evaluation**

- [ ] Dataset preprocessing and preparation
- [ ] TF-IDF + Logistic Regression baseline
- [ ] Transformer-based sarcasm classification
- [ ] Model evaluation and comparison

## License

Project-created annotations and metadata are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0) License**.

Original comment text collected from YouTube and Reddit is not relicensed under CC BY 4.0 and remains subject to the applicable platform terms and the rights of the original content creators.

Synthetic adaptations may also retain rights and restrictions associated with the underlying source material.

See [`Dataset/LICENSE.md`](Dataset/LICENSE.md) for complete licensing information.

## Project Information

**Course:** ARI 510 — Fall 2026  
**Institution:** University of Michigan–Flint  
**Student:** Chaima Zaghouani — chaimaza@umich.edu

**Project:** Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse
