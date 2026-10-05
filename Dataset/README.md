# Pilot Dataset

This folder contains the pilot dataset for the project:

**Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse**

The pilot dataset contains **50 parent–reply pairs** collected from online fan discourse. The replies are intended to contain Turkish–English code-switching and will later be annotated for sarcasm.

## Dataset Format

| Column | Description |
|---|---|
| `id` | Unique identifier for each instance |
| `platform` | Source platform: Reddit or YouTube |
| `parent_comment` | Original parent comment providing conversational context |
| `reply` | Reply that will be annotated for sarcasm |
| `timestamp` | Relative or recorded time associated with the reply |
| `language_mix` | Language-mixing category; pilot examples are marked `Mixed` |

## Dataset Preview

| ID | Platform | Parent Comment | Reply | Timestamp | Language Mix |
|---|---|---|---|---|---|
| rd_0001 | Reddit | just a heads up, Behzat Ç characters use a lot of Ankara accent | I lived in Ankara for 2 years. Angarali Turgut en favoriyim sarkici, yani ;-) | 1 year ago | Mixed |
| rd_0002 | Reddit | Arafta episode 98 and sone thoughts on the lead actors🪸🔥💫 | Herkese merhaba 🪸🔥✨️😊 I loved episode 98. ❤️🥰 It felt too short and made me realise this is how Arafta would have been if they released 1 eposode every day. | 5 months ago | Mixed |
| rd_0005 | Reddit | What sort of genres are you into? | Merhabalar! I love spooky stuff-I’d love a good crime thriller, horror or fantasy. Teşekkürler! | 2 years ago | Mixed |
| yt_0001 | YouTube | What a movie... 👋 | I cried & cried & cried 😭😭😭 Çok güzel💙 | 7 years ago | Mixed |
| yt_0009 | YouTube | Bitanesi nedir ya? Elin adamına bitanesi demek kadar anlamsız saçma ve insanı sinir eden az şey vardır insan ilişkilerinde. | They're acting like it's normal. Saçma işte. | 1 day ago | Mixed |

> The complete pilot dataset is available in [`pilot_data.csv`](pilot_data.csv).

## Data Sources

The pilot data were collected from **Reddit and YouTube** discussions related to Turkish television series, films, actors, characters, storylines, and fan conversations.

YouTube serves as a primary source of fan comments, while Reddit provides additional conversational discussions and parent–reply interactions.

## Data Collection Procedure

The data collection process focuses on finding naturally occurring Turkish–English code-switched replies in online fan discourse.

Each collected instance contains:

1. A **parent comment** that provides conversational context.
2. A **reply** that is the target of the annotation task.
3. Basic metadata, including the source platform and timestamp.

Candidate comments were manually checked to determine whether they satisfied the project's data collection criteria.

The filtering process is used only to identify suitable Turkish–English code-switched examples. **No sarcasm labels are assigned during data collection.** Sarcasm labels will be created later by human annotators.

## Inclusion Criteria

An instance is included when:

- A parent comment and reply are available.
- The discussion is related to Turkish fan discourse, such as television series, films, actors, characters, or storylines.
- The target reply contains both Turkish and English language use.
- The reply contains enough meaningful text for annotation.
- The example is not an obvious duplicate, advertisement, or spam.

For this project, **genuine Turkish–English code-switching** means that Turkish and English are meaningfully used in the target reply. A show name, character name, URL, username, acronym, or other isolated named entity alone is not considered sufficient evidence of code-switching.

Detailed inclusion and exclusion rules are provided in:

[`Data_Collection_Criteria.md`](Data_Collection_Criteria.md)

## Annotation Task

Annotators will read both the **parent comment** and the **reply** and classify the intended meaning of the reply as one of three labels:

- **Sarcastic**
- **Non-sarcastic**
- **Ambiguous / Uncertain**

If **Ambiguous / Uncertain** is selected, the annotator will also identify the main reason for the uncertainty, such as:

- Insufficient conversational context
- Drama or character context needed
- Language or expression unclear
- Tone genuinely ambiguous
- Other

Detailed annotation instructions are available in:

[`Annotation_Guidelines.md`](../Annotation/Guidelines/Annotation_Guidelines.md)

## Estimated Annotation Time

Each parent–reply pair is expected to take approximately **20–40 seconds** to annotate. Items requiring additional interpretation or an ambiguity reason may take longer.

Annotators are instructed to make their judgment using only the information presented in the annotation interface and **not to search online for additional context**.

## Dataset Size

- **Total pilot instances:** 50
- **Sources:** Reddit and YouTube
- **Unit of annotation:** Parent comment + reply pair
- **Target text:** Reply
- **Language setting:** Turkish–English code-switched discourse
- **Sarcasm labels:** Not assigned during data collection

## Sampling

The pilot dataset was created by identifying candidate Turkish–English comments from relevant online fan discussions and manually checking them against the project's inclusion and exclusion criteria.

The pilot is intended to test the annotation task, annotation guidelines, and interface before expanding the dataset.

## Missing Data

Only instances with an available parent comment and target reply are included. Examples without sufficient conversational context or meaningful textual content are excluded during collection.

## Privacy

Usernames and unnecessary personally identifying information are not included in the dataset. The dataset retains only the textual and metadata information needed for the research and annotation task.

## Files

- [`pilot_data.csv`](pilot_data.csv) — pilot dataset
- [`Data_Collection_Criteria.md`](Data_Collection_Criteria.md) — data inclusion and exclusion criteria
- [`LICENSE.md`](LICENSE.md) — licensing information for the dataset, annotations, and project-created metadata
- `README.md` — dataset documentation

## License

The **project-created annotations and metadata** are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0) License**.

The original comment text collected from **YouTube and Reddit** is not relicensed under CC BY 4.0 and remains subject to the applicable platform terms and the rights of the original content creators.

For complete licensing and data-release information, see:

[`LICENSE.md`](LICENSE.md)

## Project Information

**Course:** ARI 510 — Fall 2026  
**Institution:** University of Michigan-Flint  
**Project:** Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse  
**Graduate Student:** Chaima Zaghouani
