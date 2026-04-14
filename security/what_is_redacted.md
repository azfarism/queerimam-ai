# What Is Redacted and Why

This repository is public by design, but it is **not** a production dump.

The purpose of this file is to explain what has been intentionally removed or replaced before publication.

## 1. Production secrets

The following are **never** published:

- OpenAI API keys
- Firebase service-account credentials
- Stripe secret keys
- webhook signing secrets
- email provider secrets
- analytics write tokens
- any `.env` values from production or staging

Why:
these values could expose billing, backend access, or privileged infrastructure.

## 2. Live backend identifiers

The following are replaced with placeholders:

- vector store IDs
- internal file IDs
- assistant or response object IDs
- private storage bucket paths
- cloud project identifiers where exposure adds risk
- internal labels that map directly to production retrieval assets

Why:
even when an identifier is not a secret in the narrowest sense, it can still make replay, cloning, or target discovery easier.

## 3. User and admin data

The following are excluded:

- chat transcripts
- unresolved-question queues
- moderation or review notes
- analytics exports
- user identifiers
- email capture lists
- donation event logs

Why:
this is sensitive product and user data, and it has no place in a public repository.

## 4. Proprietary knowledge assets

The live knowledge base is not published in full.

That includes:
- proprietary curated summaries
- internal theological notes
- partner-contributed materials
- copyrighted source extracts
- synthesis documents created specifically for production retrieval

Why:
the value of queerimam.ai is not only in the UI. A large part of its distinctiveness is in how the corpus has been shaped, summarized, and operationalized.

## 5. Safety-review internals

The public repo does not disclose internal:
- confidence heuristics
- moderation or escalation triggers beyond broad public-safe descriptions
- sensitive abuse-handling logic
- edge-case routing thresholds
- operational response patterns that would be easier to game if fully public

Why:
a sensitive-domain assistant needs transparent principles, but not a blueprint for circumvention.

## 6. Environment configuration

This repo includes a `.env.example` file, but it only contains variable names.

It does **not** contain:
- real values
- real URLs that create risk
- private bucket names
- service-account JSON
- embedded secrets in example code

Why:
public documentation should help collaborators understand the stack without leaking anything operational.

## 7. What remains public

This repository still reveals a lot on purpose:

- the architectural stack
- the product method
- the public-safe system prompt
- the KB design strategy
- the evaluation philosophy
- the separation between storefront, chat runtime, and admin review

That is the right level of openness.

The method is public.
The production environment is not.
