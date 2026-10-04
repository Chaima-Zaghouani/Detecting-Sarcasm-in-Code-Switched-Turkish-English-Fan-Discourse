# Data Collection Criteria

## 1. Purpose

This document defines the inclusion and exclusion criteria used to collect data for the project **Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse**.

Each data instance consists of a **parent comment** (or post/video caption) and a **reply**. The reply is the target text that will later be annotated for sarcasm.

The purpose of the collection stage is to identify naturally occurring Turkish–English code-switched fan discourse. Sarcasm labels are not assigned during data collection.

## 2. Inclusion Criteria

A data instance can be included when all of the following conditions are satisfied:

1. The discussion is related to Turkish fan discourse, including television series, films, characters, storylines, actors, or events discussed by fans.

2. The target reply contains meaningful content in both **Turkish and English**.

3. Both languages contribute to the meaning of the reply.

4. The parent comment, post caption, or other available parent text provides conversational context for the reply.

5. The reply contains enough meaningful text for a human annotator to attempt to interpret its intended tone.

6. The item does not already contain an existing sarcasm label.

7. The parent–reply relationship can be clearly determined.

## 3. Genuine Turkish–English Code-Switching

A reply is considered code-switched when **Turkish and English are meaningfully used within the same reply**.

Example:

> Bu karakter gerçekten amazing, I can't believe bunu yaptı.

This example contains meaningful material from both Turkish and English.

The presence of a Turkish or English **person name, character name, television-show title, URL, username, hashtag, or acronym alone does not count as meaningful use of the second language**.

For example, an otherwise English reply containing only the Turkish title of a television series is not considered sufficient evidence of Turkish–English code-switching.

## 4. Exclusion Criteria

Exclude an item if any of the following applies:

- The reply is entirely Turkish.
- The reply is entirely English.
- The only word from the other language is a person's name or character name.
- The only element from the other language is the title of a television show or film.
- The apparent language mixing consists only of a URL, username, hashtag, acronym, or similar element.
- The reply contains only an isolated borrowed word and does not demonstrate meaningful Turkish–English code-switching.
- The reply is spam or an advertisement.
- The reply is a duplicate of an item already collected.
- The reply contains no meaningful textual content.
- The parent/reply relationship cannot be determined.
- There is insufficient source context to construct a valid parent-comment and reply pair.

## 5. Preservation of Original Text

The original wording of collected comments and replies should be preserved as much as possible.

Spelling, capitalization, punctuation, emojis, informal expressions, and grammatical errors should not be corrected simply to make an example appear more clearly code-switched.

Turkish or English words must **not be added to a source comment** in order to make it satisfy the code-switching criteria.

## 6. Important Collection Rule

**Do not decide whether an item is sarcastic while collecting the data.**

Data collection determines only whether an item satisfies the dataset requirements.

The labels:

- **Sarcastic**
- **Non-sarcastic**
- **Ambiguous / Uncertain**

will be assigned later during the annotation process by human annotators.

## 7. Final Verification

Before adding an item to the pilot dataset, verify that:

- The parent and reply form a valid conversational pair.
- The target reply contains meaningful Turkish and English content.
- The item is relevant to the project's fan-discourse domain.
- The original wording has been preserved.
- The item is not a duplicate, advertisement, or spam.
- No sarcasm label has been assigned during collection.
