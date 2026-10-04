# Pilot Dataset

This folder contains the pilot dataset for the project:

**Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse**

The pilot dataset contains **50 parent–reply pairs** collected from online fan discourse. Each reply is intended to contain Turkish–English code-switching and will later be annotated for sarcasm.

## Dataset Format

| Column | Description |
|---|---|
| `id` | Unique identifier for each instance |
| `platform` | Source platform, such as Reddit or YouTube |
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

> The complete dataset is available in [`pilot_data.csv`](pilot_data.csv).

## Data Collection

The pilot data were collected from **Reddit and YouTube** discussions related to Turkish television series, films, actors, characters, and fan conversations.

Each instance consists of:

1. A **parent comment** that provides conversational context.
2. A **reply** that is the target of annotation.
3. Basic metadata such as platform and timestamp.

The data were collected **without assigning sarcasm labels**. Sarcasm labels will be created during the annotation phase.

## Inclusion Criteria

An instance is included when:

- A parent comment and reply are available.
- The discussion is related to Turkish fan discourse, such as television series, films, actors, characters, or storylines.
- The reply contains Turkish and English language use.
- The reply contains enough meaningful text for annotation.
- The example is not an obvious duplicate, advertisement, or spam.

## Annotation Task

Annotators will read both the **parent comment** and the **reply** and classify the reply as:

- **Sarcastic**
- **Non-sarcastic**
- **Ambiguous / Uncertain**

For an **Ambiguous / Uncertain** label, annotators will also select the main reason for uncertainty.

Detailed annotation instructions are available in:

`Annotation/Guidelines/Annotation_Guidelines.md`

## Dataset Size

- **Total pilot instances:** 50
- **Sources:** Reddit and YouTube
- **Unit of annotation:** Parent comment + reply pair
- **Target text:** Reply
- **Language setting:** Turkish–English code-switched discourse

## Privacy

Usernames and unnecessary personally identifying information are not included in the dataset. The dataset focuses on the textual content required for the research task.

## Files

- `pilot_data.csv` — pilot dataset
- `Data_Collection_Criteria.md` — inclusion and exclusion criteria
- `README.md` — dataset documentation

## Project

ARI 510 — Fall 2026  
University of Michigan-Flint

**Project:** Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse
