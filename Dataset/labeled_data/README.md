# Labeled Data

## Overview

This folder contains the annotated dataset for the **Turkish–English Code-Switched Sarcasm Detection** project.

The annotation task is designed for five independent human annotators, each evaluating the same 800 Turkish–English code-switched parent-comment and reply pairs collected from Reddit and YouTube.

Each annotator's responses are stored in a separate CSV file to preserve individual judgments and support inter-annotator agreement analysis.

## Annotation Files

The folder contains five CSV files:

- `labeled_data_annotator1.csv`
- `labeled_data_annotator2.csv`
- `labeled_data_annotator3.csv`
- `labeled_data_annotator4.csv`
- `labeled_data_annotator5.csv`

Each file contains 800 instances, with the original dataset information and the corresponding annotation fields.

## Dataset Structure

Each CSV file contains the following columns:

| Column | Description |
|---|---|
| `id` | Unique identifier for each instance (`rd_` for Reddit and `yt_` for YouTube) |
| `platform` | Source platform (Reddit or YouTube) |
| `parent_comment` | Original parent comment providing conversational context |
| `reply` | Turkish–English code-switched reply to be classified |
| `timestamp` | Original timestamp information |
| `language_mix` | Language-mixing classification |
| `label` | Assigned sarcasm classification |
| `ambiguity_reason` | Main reason for uncertainty when the label is ambiguous |

## Annotation Labels

Each reply is classified using one of three primary labels:

- **Sarcastic:** The reply communicates irony, mockery, exaggeration, or a meaning that differs from its literal wording.
- **Non-sarcastic:** The reply expresses its intended meaning directly and sincerely.
- **Ambiguous / Uncertain:** The available context does not provide sufficient evidence to confidently determine whether the reply is sarcastic or non-sarcastic.

When an instance is classified as Ambiguous / Uncertain, the annotator selects one main reason:

1. **Insufficient conversational context:** Additional conversational information is needed.
2. **Drama/character context needed:** Knowledge of a television drama, film, episode, storyline, or character is required.
3. **Language/expression unclear:** A Turkish or English expression, idiom, slang term, or code-switched phrase is unclear.
4. **Tone genuinely ambiguous:** The reply could reasonably be interpreted as either sarcastic or sincere.
5. **Other:** Another reason prevents confident classification.

The `ambiguity_reason` field remains empty for Sarcastic and Non-sarcastic labels.

## Annotation Procedure

The annotation guidelines instruct each annotator to:

1. Read both the parent comment and the reply.
2. Interpret the intended meaning of the reply in its conversational context.
3. Select one of the three primary sarcasm labels.
4. Provide the main uncertainty reason when selecting Ambiguous / Uncertain.
5. Make independent judgments without searching online for additional context or discussing individual examples with other annotators.

The annotation interface is implemented using **Potato**, a web-based text annotation tool.

## Annotation Data Collection and Export

The annotation process uses Potato, a web-based annotation platform. Annotation responses are stored in a private Hugging Face dataset repository.

The annotation records are subsequently exported and converted into CSV format, preserving the original dataset instances, sarcasm labels, and ambiguity reasons. Separate CSV files are maintained for each annotator to support individual annotation analysis and inter-annotator agreement evaluation.

## Inter-Annotator Agreement

The five annotation files are intended for evaluating consistency across annotators.

Agreement analysis includes:

- **Cohen's Kappa:** Measures agreement between pairs of annotators while accounting for chance agreement.
- **Fleiss' Kappa:** Measures agreement across all five annotators for the three sarcasm categories.

The `id` column is used to align corresponding instances across the five files.

The `ambiguity_reason` column can also support further analysis of the factors contributing to uncertainty in Turkish–English code-switched sarcasm detection.
