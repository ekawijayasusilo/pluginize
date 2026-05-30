---
name: tech-doc-templates
description: Scaffold a new technical document from a sensible-default template. Supports RFC (Request for Comments — proposing a substantive change for team input), ADR (Architecture Decision Record — logging a decision that has converged), Design Doc (specifying how a system will be built), and Postmortem (a blameless retrospective after an incident). Use when starting any of these from scratch, or when an existing draft needs to be re-shaped onto a standard structure.
---

# Tech Doc Templates

This skill provides starter templates for common software-engineering documents. The templates live in the `templates/` subdirectory and are loaded on demand.

## When to use this skill

- The user asks to "write an RFC" or "draft an ADR" or similar.
- A new technical document needs structure and you want a sensible starting shape.
- An existing draft has all the right material but no clear structure — re-cast it onto a template.

This skill is for *scaffolding* documents. For polishing the prose inside them, use the sibling skills.

## Available templates

| Template | File | Use when… |
|---|---|---|
| RFC | `templates/rfc.md` | Proposing a substantive change that needs team input before commitment. Multiple alternatives are on the table; the decision is not yet made. |
| ADR | `templates/adr.md` | Recording an architectural decision that has converged. The decision is mostly made; this document captures *what* and *why* for future readers. |
| Design Doc | `templates/design-doc.md` | Specifying *how* to build a system or feature whose direction is broadly agreed. Implementation-focused: APIs, data model, cross-cutting concerns. |
| Postmortem | `templates/postmortem.md` | Documenting an incident after the fact — impact, causes, timeline, and follow-up actions. Blameless and retrospective. |

## Picking the right template

Four documents, four jobs. The fastest way to choose is by the question each one answers:

| Template | Answers | When |
|---|---|---|
| **RFC** | "*Should* we do this, and which way?" | Decision not yet made; you want input |
| **Design Doc** | "*How* will we build it?" | Direction agreed; you're specifying the build |
| **ADR** | "*What* did we decide, and why?" | A single decision has converged; record it |
| **Postmortem** | "*What* broke, and how do we prevent it?" | After an incident |

**Postmortem** is the easy one to place: it is the only *retrospective* document — you write it after something already happened. The other three are about work you are about to do, and they are the ones people confuse.

### RFC vs ADR

The two overlap and are often confused. The shortest distinction:

- **An RFC asks a question.** It exists to drive discussion. Author writes it, team reads and comments, decision emerges. Multiple alternatives are presented seriously.
- **An ADR answers a question.** It records a decision that has already converged. Alternatives are mentioned briefly to explain why they were rejected, not weighed at length.

A common workflow: write an RFC, debate it, then write an ADR that records the chosen outcome. The ADR lives in the repo; the RFC may or may not.

Other rough signals:

- RFCs include explicit "open questions" and "alternatives considered" sections. ADRs include "alternatives considered" briefly, and avoid open questions (open questions belong in an RFC).

### Design Doc vs RFC

The distinguishing axis is **decision-seeking vs. implementation-describing**. An RFC drives a debate to a conclusion: multiple alternatives are genuinely live, the audience is broad (often cross-team or org-wide), and the point is to *decide*. A Design Doc elaborates a direction that is already broadly agreed: it goes deep on one system's internals — APIs, data model, cross-cutting concerns — for the team that will build it. Practical tell: if the document's job is to settle *which direction*, it is an RFC; if its job is to specify *the build so engineers can execute*, it is a Design Doc. Some orgs collapse the two into one artifact — that is fine; pick the template whose sections match what you need.

### Design Doc vs ADR

A Design Doc describes a whole system's implementation; an ADR records one decision tersely. A single Design Doc may *generate* several ADRs, each capturing a key choice durably — because the Design Doc goes stale after implementation while the ADRs persist.

**Common workflow:** RFC (decide the direction) → Design Doc (detail the build) → ADRs (record the key decisions durably) → Postmortem (if it later breaks). Few projects need all four; pick what the moment calls for.

## Loading the template

When the user wants to start a document:

1. Confirm which template applies (RFC, ADR, Design Doc, or Postmortem) using the criteria above. If unclear, ask.
2. Read the corresponding template file from `templates/`.
3. Use the template as the starting structure. Fill in sections based on what the user provides.
4. The template files contain `<!-- guidance: ... -->` HTML comments inside each section explaining what goes there. Strip these comments from the final document before delivering it to the user — they are for filling-in guidance, not for the final reader.

## Related skills

When working on a document scaffolded by this skill:

- `document-structure` — for organizing the content *within* each section (BLUF for summary sections, PREP for argumentative sections, etc.).
- `writing-clearly-and-concisely` — sentence-level polish.
- `de-slop` — strip AI patterns from any draft prose.
- `audience-awareness` — each of these documents has specific readers (your team, future maintainers, incident reviewers); apply rules accordingly.

