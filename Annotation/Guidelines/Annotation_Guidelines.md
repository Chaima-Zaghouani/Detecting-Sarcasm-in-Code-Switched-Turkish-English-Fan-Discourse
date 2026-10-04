# Annotation Guidelines

## Detecting Sarcasm in Code-Switched Turkish–English Fan Discourse

### 1. Overview of the Annotation Task

The purpose of this annotation task is to identify sarcasm in Turkish–English code-switched fan discussions about Turkish television dramas, films, characters, actors, and storylines.

For each data instance, you will be shown:

- A **parent comment** that provides conversational context.
- A **reply** containing Turkish–English code-switching.

Your main task is to determine whether the reply is:

- **Sarcastic**
- **Non-sarcastic**
- **Ambiguous / Uncertain**

When **Ambiguous / Uncertain** is selected, you will also be asked to indicate the main reason why the sarcasm cannot be determined confidently.

Please read both the parent comment and the reply before assigning a label. The parent comment is important because the intended meaning of a reply may depend on the conversational context.

### 2. Annotation Labels

For each parent-comment and reply pair, select **one** of the following three labels.

#### 2.1 Sarcastic

Select **Sarcastic** when the reply says or implies something different from its literal wording, usually to mock, criticize, exaggerate, or joke ironically.

**Question to ask yourself:**  
Does the writer appear to mean something different from what the words literally say?

#### 2.2 Non-sarcastic

Select **Non-sarcastic** when the reply expresses its meaning directly and sincerely.

**Question to ask yourself:**  
Does the writer appear to mean what they wrote?

#### 2.3 Ambiguous / Uncertain

Select **Ambiguous / Uncertain** when there is not enough evidence to confidently determine whether the reply is sarcastic or non-sarcastic, even after reading the parent comment.

**Question to ask yourself:**  
Could the reply reasonably be interpreted as either sarcastic or sincere?

If you select **Ambiguous / Uncertain**, you must also indicate the **main reason** for your uncertainty.

##### Reasons for Ambiguity / Uncertainty

- **Insufficient conversational context** – More information from the conversation is needed to determine the intended tone.
- **Drama/character context needed** – Knowledge about the television drama, film, episode, storyline, or characters is needed to determine the intended tone.
- **Language/expression unclear** – A Turkish or English expression, slang term, idiom, or code-switched phrase is unclear to you.
- **Tone genuinely ambiguous** – You understand the language and available context, but the reply could still reasonably be interpreted as either sarcastic or sincere.
- **Other** – Another reason prevents you from confidently determining the intended tone. Briefly describe the reason when this option is selected.

Select **one main reason**. If more than one reason seems possible, choose the reason that most strongly affected your decision.

### 3. Decision Rules

Follow these rules when assigning a sarcasm label.

#### Rule 1: Always read both the parent comment and the reply

Do not classify the reply by itself. Read the parent comment first because it provides conversational context that may change the interpretation of the reply.

#### Rule 2: Focus on the intended meaning, not only the literal words

A reply may contain positive or negative words while communicating the opposite meaning. Consider whether the writer appears to sincerely mean what they wrote.

#### Rule 3: Look for a contrast between the reply and its context

Sarcasm may occur when the literal meaning of the reply conflicts with the situation described in the parent comment.

For example:

**Parent:** He lied to her again.  
**Reply:** Ne kadar dürüst bir adam, really amazing 🙄.

The reply literally describes the character as honest and amazing, but this conflicts with the parent comment stating that he lied again. This contrast supports a **Sarcastic** label.

#### Rule 4: Do not assume that emojis automatically indicate sarcasm

Emojis such as 🙄, 😂, 👏, or 😭 may provide useful clues about tone, but an emoji alone is not enough to determine the label. Interpret the emoji together with the parent comment and reply.

#### Rule 5: Do not assume that code-switching indicates sarcasm

All replies in this task contain Turkish–English code-switching. Mixing Turkish and English is not itself evidence of sarcasm. Determine the label based on the intended meaning of the reply and its context.

#### Rule 6: Use Ambiguous / Uncertain only when a confident decision cannot be made

Do not select **Ambiguous / Uncertain** simply because the example is difficult.

First consider the parent comment, reply, wording, tone, and other available clues.

Select **Ambiguous / Uncertain** when the available information still does not provide enough evidence to confidently choose between **Sarcastic** and **Non-sarcastic**.

#### Rule 7: If Ambiguous / Uncertain is selected, identify the main reason

Choose the reason that best explains why you cannot confidently determine the intended tone:

- Insufficient conversational context
- Drama/character context needed
- Language/expression unclear
- Tone genuinely ambiguous
- Other

If more than one reason seems possible, select the reason that had the greatest effect on your decision.

#### Rule 8: Base your decision only on the information available to you

Do not search online for the comment, television scene, film, episode, character, or storyline while annotating.

If additional knowledge about the drama, film, episode, storyline, or character is necessary to make the decision, select **Ambiguous / Uncertain** and choose **Drama/character context needed**.

### 4. Annotation Examples

The following examples illustrate how to apply the three primary sarcasm labels.

#### Example 1: Sarcastic

**Parent comment:**  
He promised he would finally tell her everything, but then he lied to her again.

**Reply:**  
Gerçekten çok dürüst, I'm impressed.

**Label:** Sarcastic

**Explanation:**  
The reply literally describes the character as very honest and says that the writer is impressed. However, the parent comment states that the character lied again. The positive wording conflicts with the situation and is being used ironically. Therefore, the reply should be labeled **Sarcastic**.

---

#### Example 2: Non-sarcastic

**Parent comment:**  
That scene made me cry. I wasn't expecting him to leave.

**Reply:**  
Ben de ağladım, that scene was gerçekten heartbreaking 😭.

**Label:** Non-sarcastic

**Explanation:**  
The reply directly agrees with the emotion expressed in the parent comment. There is no clear conflict between the literal wording and the intended meaning. The writer appears to sincerely describe the scene as heartbreaking. Therefore, the reply should be labeled **Non-sarcastic**.

---

#### Example 3: Ambiguous / Uncertain

**Parent comment:**  
He apologized to her and admitted that everything was his fault.

**Reply:**  
Vay be, character development 👏.

**Label:** Ambiguous / Uncertain

**Reason for uncertainty:** Tone genuinely ambiguous

**Explanation:**  
The reply could be sincere praise for the character's development, but it could also be an ironic reaction to the character finally admitting fault. The parent comment does not provide enough evidence to confidently distinguish between these interpretations. Therefore, the reply should be labeled **Ambiguous / Uncertain**, with **Tone genuinely ambiguous** as the reason.

### 5. Annotator Requirements

Because this task focuses on Turkish–English code-switched text, annotators should be able to understand both Turkish and English well enough to interpret the meaning and tone of the comments.

Annotators do not need specialized knowledge of Turkish television dramas or films. The parent comment will provide the primary conversational context needed for annotation.

If an annotator understands the language but believes that knowledge of a specific television drama, film, episode, storyline, or character is necessary to determine the intended tone, the item should be labeled **Ambiguous / Uncertain** with the reason **Drama/character context needed**.

If a particular word, slang expression, idiom, or code-switched phrase cannot be understood, the item should be labeled **Ambiguous / Uncertain** with the reason **Language/expression unclear**.

Annotators should not search online for additional information about television dramas, films, characters, episodes, storylines, or original comments while completing the annotation task.

### 6. Annotation Procedure

For each item, follow these steps:

1. Read the **parent comment** carefully.
2. Read the **reply** carefully.
3. Consider the meaning of the reply in relation to the parent comment.
4. Select **one** primary label:
   - Sarcastic
   - Non-sarcastic
   - Ambiguous / Uncertain
5. If you select **Ambiguous / Uncertain**, select **one main reason** for your uncertainty:
   - Insufficient conversational context
   - Drama/character context needed
   - Language/expression unclear
   - Tone genuinely ambiguous
   - Other
6. If **Other** is selected, briefly describe the reason in the provided text field.
7. Submit the annotation and continue to the next item.

Please make your own judgment for each item. Do not search online for additional context or discuss individual items with other annotators while completing the task.

### 7. Questions or Problems

If you encounter a problem with the annotation interface, instructions, or an individual data item, please contact:

**Chaima Zaghouani**  
University of Michigan-Flint  
ARI 510 – Fall 2026  
Email: chaimaza@umich.edu

Questions about the annotation procedure are welcome. However, please do not ask for the intended label of a specific item before submitting your annotation, since the goal is to collect each annotator's independent judgment.
