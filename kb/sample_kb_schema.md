# Sample Knowledge Base Schema

This document shows the **shape** of a retrieval corpus suitable for queerimam.ai without disclosing the live knowledge base.

The goal is not just to store information. The goal is to make retrieval **coherent, pastoral, and operationally useful**.

## 1. Design principles

### Canon first
One document acts as the governing philosophy and method layer. It defines:
- voice
- ethical posture
- how to handle ambiguity
- how to use scripture
- when to escalate
- what kind of answer not to give

This should be retrieved before or alongside issue-specific material.

### Topic documents should answer real user questions
Documents should not exist as vague essays if they can instead be shaped around real user intents:
- “Am I sinful for being gay?”
- “Can I pray if I feel ashamed?”
- “How do I deal with family rejection?”
- “What if I want to stay Muslim but I do not fit mosque culture?”

### Retrieval should support consistency
Each document should be structured so chunks are:
- semantically focused
- short enough to embed well
- rich enough to answer without missing key nuance
- labeled with clear metadata

## 2. Suggested corpus layers

## 2.1 Canonical philosophy layer
Purpose: the governing frame for all answers.

Suggested file type:
- `canonical_philosophy_method.md`

What it should contain:
- mission and audience
- voice rules
- theological orientation
- pastoral posture
- scripture citation rules
- ambiguity handling rules
- safety boundaries
- what to do when the KB is weak

## 2.2 Topic guides
Purpose: substantive issue-specific grounding.

Examples:
- sexuality_and_sin.md
- prayer_and_spiritual_shame.md
- family_rejection_and_boundaries.md
- trans_identity_and_dignity.md
- celibacy_choice_vs_coercion.md
- loneliness_and_belonging.md
- queer_muslim_history.md
- hadith_and_mercy.md

Each topic guide should answer:
- what the issue is
- common harms or misconceptions
- theologically relevant framing
- pastoral implications
- practical care guidance
- boundaries around certainty

## 2.3 Scholar and source summaries
Purpose: translate dense texts into retrieval-friendly synthesis.

Examples:
- scholar_summary_scott_kugle.md
- scholar_summary_imam_ludovic_mohamed_zahed.md
- scholar_summary_aminah_wadud.md
- scholar_summary_khaled_abou_el_fadl.md

Recommended structure:
- who the scholar is
- what themes they are useful for
- core arguments
- limits or cautions
- retrieval tags

## 2.4 FAQ layer
Purpose: short, high-frequency answers to recurring questions.

Examples:
- faq_is_being_gay_haram.md
- faq_can_i_lead_prayer.md
- faq_do_i_need_to_leave_islam.md
- faq_how_do_i_talk_to_allah_when_i_feel_dirty.md

FAQ documents are especially useful for:
- latency
- consistency
- handling common questions without overloading longer source files

## 2.5 Resource and support routing layer
Purpose: practical next-step guidance for users needing support.

Examples:
- resource_when_user_is_in_crisis.md
- resource_family_violence_or_coercion.md
- resource_mental_health_support.md
- resource_gender_transition_support.md

These documents should be region-aware if possible.

## 3. Suggested metadata schema

Each chunk or source document should carry metadata like this:

```yaml
id: sexuality_and_sin_001
title: Sexuality, sin, and moral agency
source_type: topic_guide
topic_tags:
  - sexuality
  - sin
  - shame
  - dignity
audience_tags:
  - queer_muslim
  - questioning_muslim
  - ally
jurisprudence_scope:
  - cross_sect
tone_tags:
  - pastoral
  - affirming
  - careful
risk_tags:
  - identity_distress
  - family_rejection
priority: high
canonical_weight: false
last_reviewed: 2026-03-01
public_safe_summary: >
  Explains how queerimam.ai approaches questions about sexuality and sin
  without collapsing identity into moral panic.
```

## 4. Chunking guidance

### Target chunk shape
A good chunk is usually:
- 200 to 600 words
- one central idea
- minimal digressions
- enough context to stand alone if retrieved

### Avoid
- giant essay-sized chunks
- multiple unrelated questions in one chunk
- citation-heavy clutter that buries the answerable idea
- repeated boilerplate at the start of every chunk

### Prefer
- explicit headings
- short paragraphs
- one question or claim per section
- plain-language summaries near dense material

## 5. Example source template

```markdown
---
id: family_rejection_and_boundaries
title: Family rejection, boundaries, and staying spiritually intact
source_type: topic_guide
topic_tags: [family, rejection, boundaries, shame]
risk_tags: [abuse_risk, housing_insecurity, depression_risk]
canonical_weight: false
---

# Family rejection, boundaries, and staying spiritually intact

## Core pastoral claim
A user can remain Muslim, dignified, and worthy before Allah even if their family
is using religion to shame or control them.

## Common user question
What do I do if my family says I am a disgrace and that Allah hates me?

## Answer shape
The response should:
- separate divine mercy from family cruelty
- avoid simplistic “just leave” language
- acknowledge emotional and financial dependency
- offer proportionate practical next steps
- escalate only if abuse, coercion, or danger is present

## Useful theological anchor
Allah's mercy and justice should not be reduced to the harshest voice in the room.

## Practical care notes
Encourage protective boundaries, external support, and worship practices that restore dignity.
```

## 6. Operational advice

### Log the questions the KB cannot answer well
The strongest KB is not the one that looks elegant on day one.
It is the one that gets better because real unanswered questions are captured and reviewed.

### Separate source truth from public wording
Some internal files can be dense, but retrieval-facing summaries should be optimized for what the model actually needs in context.

### Keep a review date
Sensitive-domain knowledge should always have a visible review date, especially when practical guidance, institutional references, or external resources may change.

## 7. Minimum viable corpus

A strong MVP corpus does not need hundreds of documents.

A credible starting point is:
- 1 canonical philosophy document
- 10 to 20 topic guides
- 10 to 20 FAQ files
- 5 to 10 scholar summaries
- 5 to 10 resource-routing files

The key is not volume alone. The key is **retrieval shape, consistency, and reviewability**.
