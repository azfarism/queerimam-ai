# queerimam.ai — Public Architecture, Trust Design, and Product Method

A public, sanitized showcase of how **queerimam.ai** is designed: not as a generic chatbot, but as a high-context pastoral AI product for LGBTQ+ Muslims and their allies.

**Stack at a glance:** Framer + FlutterFlow + Firebase + OpenAI + human review loops.

This repository is intentionally selective. It is meant to reveal the **method**, **architecture**, **trust design**, **prompt discipline**, and **evaluation logic** behind queerimam.ai without exposing production secrets, live user data, or the proprietary knowledge base.

## Why this repository exists

Many AI demos can look polished in public while hiding weak operations underneath. That matters even more in a sensitive domain.

queerimam.ai was built with a different premise: a product like this has to earn trust through **structure**, not branding alone. That means the public-facing story, the knowledge design, the answer style, the privacy choices, and the review loops all have to work together.

This repository exists to make that method legible.

## What queerimam.ai is

queerimam.ai is an AI imam designed to support LGBTQ+ Muslims and their allies with answers that are:

- warm without sounding generic
- theologically grounded without becoming rigid or punitive
- queer-affirming without slipping into slogan-only language
- operationally accountable rather than theatrically confident

The aim is not to produce the loudest or most maximalist answer. The aim is to produce an answer that feels humane, coherent, and trustworthy.

## What makes this product distinct

The interesting part is not that it “uses AI.” The interesting part is the product logic.

### 1) Canon-first retrieval
The system is designed to prioritize a governing philosophy or method document before consulting topic-specific materials. That keeps answers coherent across theology, ethics, pastoral care, and safety.

### 2) Pastoral voice discipline
The assistant is tuned to sound like a caring imam rather than a product manual, legal memo, or over-clinical support bot.

### 3) Controlled ambiguity handling
If a user message clearly lacks context, the assistant asks exactly one clarifying question. Otherwise, it answers directly.

### 4) Scripture citation discipline
When a user explicitly asks an Islamic question, the system includes exactly one Qur'anic anchor or one brief hadith rather than dumping citations for show.

### 5) Safety without flattening the user
The assistant does not default to crisis-script language. It escalates only when the user signals imminent harm, abuse, coercion, or suicidality.

### 6) Human-in-the-loop improvement
Low-confidence or unresolved questions are routed into review so the knowledge base, prompt logic, and answer quality can improve deliberately over time.

## Trust by design

One of the core claims behind queerimam.ai is that trust should not be an aesthetic layer added at the end. It should be designed into the product from the beginning.

That trust architecture includes:

- **Accountability by identity** — the product is attached to a real founder and public body of thought rather than a faceless bot brand
- **Transparency of lens and sources** — users are told what kind of framework the assistant is working from
- **Privacy-first onboarding** — users can try the product without being forced to disclose identity immediately
- **Grounded answering** — the assistant is shaped by curated knowledge, not raw model improvisation alone
- **Uncertainty pathways** — the system can surface unresolved questions rather than hallucinating certainty
- **Operational review loops** — logging, unanswered-question review, and admin workflows allow correction and iteration

Read the full public breakdown here: [`docs/trust-by-design.md`](docs/trust-by-design.md)

## Public architecture

Based on the hybrid MVP design:

- **Framer** hosts the main storefront at `queerimam.ai`
- **FlutterFlow** powers the chat experience and admin interface
- **Firebase** handles hosting, auth, data storage, and Cloud Functions
- **OpenAI** powers generation and retrieval-backed answering
- **Admin workflows** support unanswered-question review, metrics, and content iteration

A simplified version of the core flow:

1. A visitor lands on the main site and enters chat
2. The chat session runs through a Firebase-hosted frontend
3. The request is passed to a backend function rather than calling the model directly from the client
4. The backend sends a structured request to the model with instructions and retrieval tools
5. The answer returns to the user
6. The interaction is logged for analytics and quality review
7. Low-confidence cases can be triaged into an admin queue for follow-up improvement

For a fuller walkthrough, see [`docs/architecture.md`](docs/architecture.md).

## Repository contents

- [`README.md`](README.md) — what queerimam.ai is, why it exists, and the public system design
- [`docs/architecture.md`](docs/architecture.md) — Framer + FlutterFlow + Firebase + backend flow
- [`docs/trust-by-design.md`](docs/trust-by-design.md) — the public trust architecture and product-safety decisions
- [`docs/github-upload-checklist.md`](docs/github-upload-checklist.md) — browser-only upload and formatting checklist
- [`prompts/public_system_prompt.json`](prompts/public_system_prompt.json) — sanitized public prompt/config
- [`kb/sample_kb_schema.md`](kb/sample_kb_schema.md) — sample knowledge-base structure and metadata model
- [`evals/sample_questions.jsonl`](evals/sample_questions.jsonl) — representative edge cases and expected behaviors
- [`security/what_is_redacted.md`](security/what_is_redacted.md) — what is intentionally omitted from this repo
- [`.env.example`](.env.example) — environment variable names only, with no real values

## What is intentionally not included

This is not a dump of the live production system.

This repository does **not** include:

- production API keys
- service-account credentials
- live vector store IDs
- production Firebase values beyond safe placeholders
- user conversations or analytics exports
- the proprietary knowledge corpus
- copyrighted or partner-contributed materials
- internal review notes or moderation logs
- operational thresholds that would make the system easier to game

See [`security/what_is_redacted.md`](security/what_is_redacted.md) for the full breakdown.

## Product principles

### Warmth over performance theater
The goal is not to sound maximally smart. The goal is to sound trustworthy, grounded, and humane.

### Structure over improvisation
Answers should feel natural, but the system itself should be highly structured: retrieval order, tone rules, citation rules, escalation logic, and review loops all matter.

### Retrieval over bluffing
If the system has relevant grounded material, it should use it. If not, it should answer modestly rather than inventing authority.

### Trust as an operational discipline
A sensitive product should be reviewable, improvable, and corrigible. Trust is not a launch claim. It is an operating model.

## Why this repository is useful

This repository is meant to be useful to three audiences:

- **Engineers** who want to understand the architecture and boundaries
- **Partners, journalists, and funders** who want to see that the product has a real operating model
- **Builders in sensitive domains** who want a public example of how warmth, safety, and backend rigor can coexist

The core signal it aims to send is simple:

**queerimam.ai is not just a chatbot. It is a deliberately designed AI product with a clear theological method, a clear UX voice, and a clear operational improvement loop.**

## Future extensions

Possible next layers include:

- multilingual support
- scholar or expert review workflows
- tighter evaluation harnesses for tone, theology, and harm-prevention
- channel expansion across additional platforms and interfaces
- monetization flows tied to trust-preserving user journeys

## Contact / collaboration

This public repository is meant to make the underlying method legible to collaborators, engineers, funders, and institutional partners without exposing production-sensitive information.

If you are exploring partnerships, implementation, research, or infrastructure for sensitive-domain AI systems, this is the level at which the product is meant to be understood in public.
