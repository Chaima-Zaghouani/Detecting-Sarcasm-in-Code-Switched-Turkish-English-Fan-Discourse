# Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse

ARI 510 project on sarcasm detection in Turkish–English code-switched fan discourse.

## Overview

This project investigates sarcasm detection in **Turkish–English code-switched fan discourse**, where users naturally switch between Turkish and English while discussing television series, films, actors, characters, and storylines.

Sarcasm can be challenging to identify because its interpretation often depends on conversational context, tone, irony, emojis, and cultural references. Code-switching introduces an additional challenge because meaning may be expressed across two languages within the same conversation.

The goal of this project is to develop a **carefully annotated dataset** and later evaluate machine-learning approaches for automatically detecting sarcasm in Turkish–English code-switched text.

## Phase 1: Dataset and Annotation

The first phase of the project focuses on developing and validating the annotation process.

A pilot dataset of **50 parent–reply pairs** was collected from online fan discourse:

- **YouTube:** 28 pairs (56%)
- **Reddit:** 22 pairs (44%)

The **parent comment** provides conversational context, while the **reply** is the target text that is annotated for sarcasm.

No sarcasm labels were assigned during data collection. Labels are created separately through human annotation.

## Annotation Labels

Each reply is classified into one of three categories:

- **Sarcastic** — the intended meaning differs from the literal wording, such as through irony, mock praise, or ridicule.
- **Non-sarcastic** — the reply communicates its meaning directly and sincerely.
- **Ambiguous / Uncertain** — there is not enough evidence to confidently determine whether the reply is sarcastic.

When **Ambiguous / Uncertain** is selected, annotators also identify the main reason for their uncertainty:

- Insufficient conversational context
- Drama/character context needed
- Language/expression unclear
- Tone genuinely ambiguous
- Other

## Annotation Interface

The annotation interface was developed using **Potato**.

Annotators independently:

1. Read the parent comment and reply.
2. Select one sarcasm label.
3. If **Ambiguous / Uncertain** is selected, identify the main reason for uncertainty.
4. Complete the assigned examples without searching online for additional context.

The annotation interface is hosted online for independent annotation.

## Internal Pilot

The complete 50-item dataset was internally annotated to test the annotation guidelines and interface.

The internal pilot produced:

- **Sarcastic:** 19
- **Non-sarcastic:** 18
- **Ambiguous / Uncertain:** 13

These internal annotations are used to evaluate the annotation setup and are **not considered final ground-truth labels**.

Final labels will be determined after collecting annotations from multiple annotators, evaluating **inter-annotator agreement**, and reviewing cases with substantial disagreement.

## Dataset Documentation

Detailed dataset documentation is available in the [`Dataset`](Dataset/) directory:

- [`pilot_data.csv`](Dataset/pilot_data.csv) — 50-item pilot dataset
- [`README.md`](Dataset/README.md) — dataset documentation
- [`Data_Collection_Criteria.md`](Dataset/Data_Collection_Criteria.md) — inclusion and exclusion criteria
- [`LICENSE.md`](Dataset/LICENSE.md) — dataset licensing information

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

**Data Collection → Annotation Guidelines → Pilot Dataset → Annotation Interface → Independent Human Annotation → Inter-Annotator Agreement → Disagreement Resolution → Ground-Truth Labels → Dataset Expansion → Modeling**

## Planned Modeling

After completing the annotation and dataset-development stages, the project will evaluate sarcasm classification approaches including:

- **TF-IDF + Logistic Regression** as a baseline
- **Transformer-based models** for contextual sarcasm classification

The models will be evaluated on their ability to identify sarcasm in Turkish–English code-switched text.

## Repository Structure

```text
Detecting-Sarcasm-in-Code-Switched-Turkish-English-Fan-Discourse/
│
├── README.md
│
├── Dataset/
│   ├── pilot_data.csv
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

**Phase 1**

- [x] Pilot dataset collected
- [x] Data collection criteria defined
- [x] Annotation guidelines developed
- [x] Potato annotation interface implemented
- [x] Annotation workflow tested
- [x] Internal 50-item pilot completed
- [x] Dataset documentation and licensing prepared
- [ ] Independent classmate annotation
- [ ] Inter-annotator agreement analysis
- [ ] Disagreement resolution and ground-truth labels
- [ ] Dataset expansion

## License

Project-created annotations and metadata are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0) License**.

Original comment text collected from YouTube and Reddit is not relicensed under CC BY 4.0 and remains subject to the applicable platform terms and the rights of the original content creators.

See [`Dataset/LICENSE.md`](Dataset/LICENSE.md) for complete licensing information.

## Project Information

**Course:** ARI 510 — Fall 2026  
**Institution:** University of Michigan-Flint  
**Student:** Chaima Zaghouani - chaimaza@umich.edu

**Project:** Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse
