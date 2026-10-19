# Annotation

This folder contains the annotation materials for the project **Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse**.

## Annotation Overview

The annotation task involves five independent human annotators evaluating 800 Turkish–English code-switched parent-comment and reply pairs collected from Reddit and YouTube.

Annotators are instructed to read both the parent comment and the corresponding reply before assigning one of three primary labels:

- **Sarcastic**
- **Non-sarcastic**
- **Ambiguous / Uncertain**

For replies labeled **Ambiguous / Uncertain**, annotators also identify the main reason for their uncertainty. This additional annotation was introduced based on feedback received on the project proposal.

The possible reasons are:

- Insufficient conversational context
- Drama/character context needed
- Language/expression unclear
- Tone genuinely ambiguous
- Other

## Annotation Interface

The annotation interface is implemented using **Potato**, a web-based annotation platform.

The interface presents the parent comment and reply separately, allowing annotators to select a primary sarcasm label and, when necessary, provide an ambiguity reason.

Annotation responses are backed up to a private Hugging Face dataset repository and exported into CSV format.

## Folder Structure

This folder contains:

- **Guidelines/** – Detailed annotation instructions, label definitions, decision rules, and examples.
- **Interface/** – Configuration and instructions for the Potato annotation interface.
- **Results/** – Materials and outputs related to annotation results, where applicable.

## Labeled Dataset

The five annotator CSV files are maintained in the [`Dataset/labeled_data/`](../Dataset/labeled_data/) folder.

Each file contains 800 parent-comment and reply pairs, along with the corresponding sarcasm labels and ambiguity reasons.

The files are named:

- `labeled_data_annotator1.csv`
- `labeled_data_annotator2.csv`
- `labeled_data_annotator3.csv`
- `labeled_data_annotator4.csv`
- `labeled_data_annotator5.csv`

For detailed information about the labeled dataset structure and annotation categories, see [`Dataset/labeled_data/README.md`](../Dataset/labeled_data/README.md).

## Inter-Annotator Agreement

The annotation results will be used to evaluate agreement across the five annotators.

The planned agreement analysis includes:

- **Cohen's Kappa:** Pairwise agreement between annotators.
- **Fleiss' Kappa:** Overall agreement across all five annotators.

The analysis will assess consistency in sarcasm classification and help identify sources of disagreement in Turkish–English code-switched conversations.
