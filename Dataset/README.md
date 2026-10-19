# Turkish–English Code-Switched Sarcasm Dataset

This folder contains the pilot, expanded, and labeled datasets for the project:

**Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse**

The project investigates sarcasm detection in Turkish–English code-switched online conversations. Each dataset instance consists of a parent comment providing conversational context and a corresponding reply that serves as the target for sarcasm annotation.

The dataset contains **800 parent–reply pairs**, including the initial 50-example pilot dataset. The expanded dataset combines collected social-media comments with synthetically adapted Turkish–English code-switched replies.

The dataset includes an unlabeled version and five separately maintained human annotation files.

## Dataset Files

| File / Folder | Description | Instances |
|---|---|---|
| `pilot_data.csv` | Initial pilot dataset for testing the annotation process | 50 |
| `unlabeled_data.csv` | Expanded dataset prepared for sarcasm annotation | 800 |
| `labeled_data/` | Folder containing five annotator CSV files and a README describing the annotation process and labels | 800 per annotator |

The 800-example dataset is the primary dataset for the annotation task. The pilot examples are included in the expanded dataset and should not be counted as additional independent instances.

### Labeled Data

The [`labeled_data/`](labeled_data/) folder contains five CSV files:

- `labeled_data_annotator1.csv`
- `labeled_data_annotator2.csv`
- `labeled_data_annotator3.csv`
- `labeled_data_annotator4.csv`
- `labeled_data_annotator5.csv`

Each file contains the same 800 parent–reply pairs, together with the corresponding annotator's sarcasm classifications and ambiguity reasons.

The annotation workflow uses Potato, a web-based text annotation platform. Annotation responses are backed up to a private Hugging Face dataset repository and exported into CSV format.

The files are maintained separately to preserve individual annotation judgments and support inter-annotator agreement analysis.

For additional details about the labeled dataset, see [`labeled_data/README.md`](labeled_data/README.md).

## Dataset Format

The pilot and expanded unlabeled CSV files follow the same six-column structure.

| Column | Description |
|---|---|
| `id` | Unique identifier for each instance |
| `platform` | Source platform associated with the original discussion: Reddit or YouTube |
| `parent_comment` | Parent comment providing conversational context |
| `reply` | Target reply to be annotated for sarcasm |
| `timestamp` | Relative or recorded timestamp associated with the original discussion |
| `language_mix` | Language-mixing category; examples are marked `Mixed` |

Each row represents one parent–reply pair. The reply is the target of the sarcasm classification task, while the parent comment provides context for interpretation.

The labeled CSV files preserve these six columns and include two additional annotation columns:

| Column | Description |
|---|---|
| `label` | Sarcasm classification: `sarcastic`, `non-sarcastic`, or `ambiguous` |
| `ambiguity_reason` | Main reason for uncertainty when an instance is classified as ambiguous |

The `ambiguity_reason` field remains empty for sarcastic and non-sarcastic instances.

## Dataset Preview

| ID | Platform | Parent Comment | Reply | Timestamp | Language Mix |
|---|---|---|---|---|---|
| rd_0001 | Reddit | just a heads up, Behzat Ç characters use a lot of Ankara accent | I lived in Ankara for 2 years. Angarali Turgut en favoriyim sarkici, yani ;-) | 1 year ago | Mixed |
| rd_0002 | Reddit | Arafta episode 98 and sone thoughts on the lead actors🪸🔥💫 | Herkese merhaba 🪸🔥✨️😊 I loved episode 98. ❤️🥰 It felt too short and made me realise this is how Arafta would have been if they released 1 episode every day. | 5 months ago | Mixed |
| rd_0005 | Reddit | What sort of genres are you into? | Merhabalar! I love spooky stuff—I’d love a good crime thriller, horror or fantasy. Teşekkürler! | 2 years ago | Mixed |
| yt_0001 | YouTube | What a movie... 👋 | I cried & cried & cried 😭😭😭 Çok güzel💙 | 7 years ago | Mixed |

The complete unlabeled datasets are available in [`pilot_data.csv`](pilot_data.csv) and [`unlabeled_data.csv`](unlabeled_data.csv).

## Data Sources

The dataset uses discussions associated with **Reddit and YouTube**.

The initial pilot collection focused on Turkish television series, films, actors, characters, storylines, and fan conversations.

The expanded dataset also includes additional Reddit conversational threads covering broader topics. These examples provide a wider range of conversational contexts for investigating sarcasm.

The `platform` field identifies the platform associated with the source discussion. It does not necessarily indicate that the final code-switched wording was posted verbatim on that platform.

## Data Collection and Expansion Procedure

The dataset was developed in two stages.

### Stage 1: Pilot Data Collection

An initial set of 50 parent–reply pairs was assembled from Reddit and YouTube discussions.

Candidate examples were examined for Turkish–English language use, conversational context, and suitability for sarcasm annotation.

The pilot dataset was intended to test the annotation guidelines, task design, and annotation interface.

### Stage 2: Dataset Expansion

The dataset was expanded to 800 parent–reply pairs using additional Reddit conversational data and Turkish–English code-switching adaptations.

For synthetically adapted examples, Turkish expressions were incorporated into English-language replies to create bilingual conversational text.

The expanded dataset was subsequently reviewed and corrected to address identified issues such as missing language mixing, awkward expressions, and formatting inconsistencies.

Because some replies were modified, the expanded dataset should be considered **partly synthetic**, rather than a collection of exclusively naturally occurring Turkish–English social-media comments.

The synthetic adaptations preserve the general conversational context but are not presented as verbatim original user posts.

**No sarcasm labels were assigned during data collection or expansion.** Sarcasm labels are maintained separately in the annotation files.

## Inclusion Criteria

An instance is intended to satisfy the following criteria:

- A parent comment and corresponding reply are available.
- The parent comment provides meaningful conversational context.
- The target reply contains meaningful Turkish and English language use.
- The reply contains sufficient information for sarcasm annotation.
- The instance is not an obvious duplicate, advertisement, or spam.

For this project, **Turkish–English code-switching** refers to the meaningful use of both languages within the target reply.

A television show name, character name, URL, username, acronym, or other isolated named entity alone is not considered sufficient evidence of code-switching.

Synthetic language-mixing examples are also subject to linguistic quality review. Automatic language checks do not guarantee that every example is fully natural or linguistically valid.

Detailed criteria are available in:

[`Data_Collection_Criteria.md`](Data_Collection_Criteria.md)

## Annotation Task

The annotation task involves five independent human annotators examining both the **parent comment** and the **target reply** to determine whether the reply expresses sarcasm.

Each instance is assigned one of three labels:

| Label | Category | Description |
|---|---|---|
| 1 | Sarcastic | The reply expresses sarcasm, irony, or a meaning that contrasts with its literal wording |
| 0 | Non-sarcastic | The reply does not express sarcasm |
| U | Ambiguous / Uncertain | The intended meaning cannot be determined confidently |

For examples labeled **Ambiguous / Uncertain**, annotators identify the primary reason for uncertainty:

- Insufficient conversational context
- Drama/character context needed
- Language/expression unclear
- Tone genuinely ambiguous
- Other

The annotation task focuses on interpreting the reply in relation to its parent comment. The presence of Turkish words, negative sentiment, or strong emotional expressions alone does not establish sarcasm.

Detailed annotation instructions are available in:

[`Annotation_Guidelines.md`](../Annotation/Guidelines/Annotation_Guidelines.md)

## Annotation Procedure and Data Export

The annotation interface is implemented using **Potato**, a web-based annotation platform.

Five human annotators independently evaluate the same 800 parent–reply pairs using the project's annotation guidelines.

For each instance, annotators:

1. Read the parent comment and reply.
2. Interpret the intended meaning of the reply in its conversational context.
3. Select one of the three primary sarcasm labels.
4. Select one main uncertainty reason when assigning Ambiguous / Uncertain.
5. Make independent judgments without searching online for additional context or discussing individual examples with other annotators.

Annotation responses are backed up to a private Hugging Face dataset repository.

The annotation records are exported and converted into CSV format, preserving the original dataset instances, sarcasm labels, and ambiguity reasons.

Each annotator's responses are stored in a separate CSV file in the [`labeled_data/`](labeled_data/) folder.

This structure supports individual annotation analysis and subsequent inter-annotator agreement evaluation.

## Estimated Annotation Time

Each parent–reply pair is expected to require approximately **20–40 seconds** for annotation.

Longer comments and examples requiring additional interpretation may take more time.

Annotators are instructed to use only the provided conversational context and not to search online for additional information.

## Dataset Size

| Property | Value |
|---|---|
| Pilot dataset | 50 parent–reply pairs |
| Expanded dataset | 800 parent–reply pairs |
| Reddit examples in expanded dataset | 772 (96.5%) |
| YouTube examples in expanded dataset | 28 (3.5%) |
| Number of annotators | 5 |
| Labeled dataset files | 5 CSV files |
| Instances per annotator | 800 |
| Unit of annotation | Parent comment + reply pair |
| Target text | Reply |
| Language setting | Turkish–English code-switched discourse |
| Sarcasm labels | Sarcastic, Non-sarcastic, Ambiguous / Uncertain |
| Annotation method | Human annotation using Potato |

The expanded dataset includes both naturally collected and synthetically adapted material.

The source distribution is uneven, with Reddit representing the majority of the expanded dataset. This imbalance should be considered when interpreting experimental results.

## Sampling

The pilot dataset was assembled by identifying candidate comments from relevant online fan discussions and reviewing them against the project's inclusion and exclusion criteria.

The expanded dataset incorporates additional conversational material and synthetic Turkish–English adaptations.

Consequently, the expanded dataset is not a random or statistically representative sample of all Turkish–English code-switched social-media discourse.

The dataset is intended for exploratory research into sarcasm annotation and classification in bilingual conversational text.

## Data Quality and Limitations

The expanded dataset has undergone structural checks and text correction.

The following limitations remain relevant:

- Some code-switched replies were synthetically constructed rather than written by bilingual social-media users.
- Certain Turkish expressions may occur repeatedly across different examples.
- Some replies are considerably longer than others.
- The dataset contains a substantial imbalance between Reddit and YouTube examples.
- The expanded dataset includes conversations beyond Turkish television and fan discourse.
- Human linguistic review is necessary to establish the naturalness of individual code-switching examples.

These characteristics should be considered when interpreting annotation results and evaluating machine-learning models.

## Inter-Annotator Agreement

The five annotation files support evaluation of consistency across annotators.

The agreement analysis will include:

- **Cohen's Kappa:** Measures agreement between pairs of annotators while accounting for chance agreement.
- **Fleiss' Kappa:** Measures agreement across all five annotators for the three sarcasm categories.

The `id` column is used to align corresponding instances across the five annotation files.

The `ambiguity_reason` column can also support additional analysis of the factors contributing to uncertainty in Turkish–English code-switched sarcasm detection.

## Missing Data

The dataset is structured to retain a parent comment, reply, platform, timestamp, language-mixing category, and unique identifier for each instance.

Sarcasm labels are intentionally absent from `unlabeled_data.csv` and are stored separately in the annotation CSV files.

The `ambiguity_reason` field is left empty when an instance is classified as sarcastic or non-sarcastic.

## Privacy

The dataset does not include usernames as a dedicated metadata field.

Unnecessary personal identifiers should be excluded where possible. Original text, quotations, and links may nevertheless contain identifying information and should be reviewed before public redistribution.

Annotation backups are maintained in a private Hugging Face dataset repository.

## Files

- [`pilot_data.csv`](pilot_data.csv) — initial 50-example pilot dataset
- [`unlabeled_data.csv`](unlabeled_data.csv) — expanded 800-example unlabeled dataset
- [`labeled_data/`](labeled_data/) — folder containing five annotation CSV files
- [`labeled_data/README.md`](labeled_data/README.md) — documentation of the labeled dataset, annotation categories, and agreement analysis
- [`Data_Collection_Criteria.md`](Data_Collection_Criteria.md) — data inclusion and exclusion criteria
- [`LICENSE.md`](LICENSE.md) — dataset licensing and redistribution information
- `README.md` — main dataset documentation

## License

The **project-created annotations and metadata** are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0) License**.

The original comment text collected from **Reddit and YouTube** is not relicensed under CC BY 4.0 and remains subject to the applicable platform terms and the rights of the original content creators.

Synthetic modifications do not automatically eliminate rights or restrictions associated with the underlying source text.

For complete licensing and data-release information, see:

[`LICENSE.md`](LICENSE.md)

## Project Information

**Course:** ARI 510 — Fall 2026  
**Institution:** University of Michigan–Flint  
**Project:** Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse  
**Graduate Student:** Chaima Zaghouani

## Current Project Status

- Pilot dataset collected: **50 examples**
- Expanded unlabeled dataset prepared: **800 examples**
- Dataset uploaded to GitHub
- Human sarcasm annotation: **Completed — five annotators**
- Labeled datasets: **Five CSV files, 800 instances each**
- Annotation records backed up to Hugging Face and converted into CSV format
- Inter-annotator agreement evaluation: **Planned**
- Model training and evaluation: **Planned**

The next stage of the project is to evaluate inter-annotator agreement using Cohen's kappa and Fleiss' kappa, followed by the development and evaluation of sarcasm detection models.
