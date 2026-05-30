---
name: tech-doc-templates
description: Scaffold a new technical document from a sensible-default template. Currently supports RFC (Request for Comments — proposing a substantive change for team input) and ADR (Architecture Decision Record — logging a decision that has converged). Use when starting a new RFC or ADR from scratch, or when an existing draft needs to be re-shaped onto a standard structure.
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

## RFC vs ADR — picking between them

The two documents overlap and are often confused. The shortest distinction:

- **An RFC asks a question.** It exists to drive discussion. Author writes it, team reads and comments, decision emerges. Multiple alternatives are presented seriously.
- **An ADR answers a question.** It records a decision that has already converged. Alternatives are mentioned briefly to explain why they were rejected, not weighed at length.

A common workflow: write an RFC, debate it, then write an ADR that records the chosen outcome. The ADR lives in the repo; the RFC may or may not.

Other rough signals:

- RFCs tend to be longer (2-10 pages). ADRs tend to be shorter (half a page to two pages).
- RFCs include explicit "open questions" and "alternatives considered" sections. ADRs include "alternatives considered" briefly, and avoid open questions (open questions belong in an RFC).
- If the document needs to be *read* widely, it is probably an RFC. If it needs to be *found* later by someone asking "why did we do it this way," it is probably an ADR.

## Loading the template

When the user wants to start a document:

1. Confirm which template applies (RFC or ADR) using the criteria above. If unclear, ask.
2. Read the corresponding template file from `templates/`.
3. Use the template as the starting structure. Fill in sections based on what the user provides.
4. The template files contain `<!-- guidance: ... -->` HTML comments inside each section explaining what goes there. Strip these comments from the final document before delivering it to the user — they are for filling-in guidance, not for the final reader.

## Important caveat — RFC format is team-specific

**There is no single canonical RFC format.** Rust RFCs, Python PEPs, IETF RFCs, and internal company RFCs all differ. The template provided here is a sensible default with the common sections — it is not "the" RFC format.

If the user's team or project already has an RFC template or process (in their repo, in a `RFC_TEMPLATE.md` file, in an existing RFC's structure), use *that* instead. The bundled template is a fallback for greenfield situations.

ADRs are more standardised — the Michael Nygard format (Context / Decision / Consequences) is widely adopted with minor variations — so the bundled ADR template is usually a safer default.

## Related skills

When working on a document scaffolded by this skill:

- `document-structure` — for organizing the content *within* each section (BLUF for summary sections, PREP for argumentative sections, etc.).
- `writing-clearly-and-concisely` — sentence-level polish.
- `de-slop` — strip AI patterns from any draft prose.
- `audience-awareness` — RFCs and ADRs have specific readers (your team, future maintainers); apply rules accordingly.

