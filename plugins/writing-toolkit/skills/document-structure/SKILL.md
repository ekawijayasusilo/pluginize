---
name: document-structure
description: Organize whole documents using established structural patterns — BLUF, inverted pyramid, PREP, SCQA, and classical lead/body/close. Use when starting a new document, restructuring an existing one, or when sentence-level edits aren't enough because the document's organization itself is the problem. Operates at the document level, not the sentence level.
---

# Document Structure

Sentence-level polish can't fix a poorly organized document. This skill provides structural patterns for organizing prose at the document level: which information goes first, what shape the argument takes, how the reader moves through the piece.

## When to use this skill

- Starting a new document and unsure how to organize it.
- A document is technically clean but feels unfocused — likely a structure problem.
- The reader needs to be able to stop partway through and still get the key information.
- A draft has the right material but in the wrong order.

For sentence-level rules, use `writing-clearly-and-concisely`. For matching structure to audience, use `audience-awareness`.

## The patterns

### BLUF — Bottom Line Up Front

State the conclusion, recommendation, or key takeaway in the first one or two sentences. Then support it.

When to use: memos, decision documents, status updates, executive-facing writing, any context where the reader is busy and may stop reading at any point.

Why it works: most readers do not finish documents. BLUF guarantees the most important information reaches even the readers who only read the first paragraph.

Example structure:

```
Recommendation: migrate the user service to Postgres by Q3.

The current MySQL setup is hitting connection-pool limits during peak traffic
and our schema has outgrown what MySQL handles well. Postgres gives us proper
JSON support, better concurrent-write performance, and aligns with what the
platform team is already running.

[supporting detail follows]
```

Common mistake: hiding the recommendation in a "Conclusion" section at the end. By the time the reader reaches it, they have either skipped or formed their own conclusion.

### Inverted pyramid

Order facts from most important to least important. The reader can stop at any point and still have the key information.

When to use: news, announcements, incident reports, change announcements, release notes.

Why it works: news writers developed this pattern because typesetters cut articles from the bottom to fit space. Readers behave the same way — they cut from the bottom by stopping reading. Put the most important facts where the reader will definitely see them.

Example shape:

1. Lead paragraph: what happened, when, who is affected.
2. Key details: numbers, scope, impact.
3. Background: how this came about.
4. Context: related events, history.
5. Future: what happens next.

Common mistake: chronological order ("first we did X, then we did Y, then we discovered the issue…"). Save chronology for the postmortem section. Lead with the outcome.

### PREP — Point, Reason, Example, Point

A paragraph-level pattern for persuasive writing.

1. **Point**: state the claim.
2. **Reason**: why the claim is true.
3. **Example**: concrete evidence supporting the reason.
4. **Point**: restate the claim, now grounded.

When to use: persuasive paragraphs, sections of a proposal arguing for a particular decision, blog posts making an argument.

Example:

> Code review is more valuable as a teaching moment than as a defect filter. Most defects that matter slip past reviewers anyway — the ones that get caught are usually style or naming nits a linter would also catch. Where review pays off is when a senior engineer explains *why* a pattern is preferred, and that knowledge propagates to the rest of the team. Treat code review as a teaching channel, and the catch-defects function becomes a side benefit rather than the goal.

Common mistake: stopping after Point + Reason. Without the Example, the argument is just an opinion. Without the closing Point, the reader is left to draw their own conclusion (and may not draw the right one).

### SCQA — Situation, Complication, Question, Answer

McKinsey-style framing for analytical documents. Sets up the problem so the reader understands why the answer matters.

1. **Situation**: the relevant context the reader already knows or accepts.
2. **Complication**: what changed or what is now wrong.
3. **Question**: the question the document answers.
4. **Answer**: the answer.

When to use: analysis documents, consulting-style writeups, strategy memos, anything where the answer only makes sense once the question is clear.

Example shape:

> **Situation**: our authentication service has handled login flow for all our products for five years.
>
> **Complication**: three new acquired products use their own identity providers, and the synchronization between them and our service now causes more incidents than it prevents.
>
> **Question**: should we consolidate onto a single identity provider, federate, or accept the operational cost?
>
> **Answer**: federate via OIDC. Consolidation is too disruptive given the current cycle; the operational cost will grow as we acquire more products; federation has a clear migration path and matches industry norms.

Common mistake: skipping the Complication. Without it, the Answer reads as an opinion floating in space. The Complication is what makes the Question matter.

### Lead, body, close

The classical essay or article structure.

- **Lead**: sets up the topic and gives the reader a reason to keep reading. Can be an anecdote, a striking fact, a question, a vivid scene. Not BLUF — the lead invites, it does not conclude.
- **Body**: develops the topic. Multiple paragraphs, each making a distinct point that supports the whole.
- **Close**: lands the piece. Returns to something from the lead, draws a conclusion, or leaves the reader with a thought.

When to use: essays, blog posts, opinion pieces, narrative non-fiction. Generally not for technical or business writing — those have better-fitting patterns above.

Common mistake: writing a lead that is really an abstract or BLUF. An essay lead invites the reader in; a memo BLUF tells them the answer immediately. Different goals, different forms.

## Technical documentation modes (Diataxis)

The patterns above (BLUF, inverted pyramid, PREP, SCQA, lead/body/close) are for prose. Technical documentation has its own information architecture, and the most useful framework is [Diataxis](https://diataxis.fr/) — four distinct modes, each serving a different reader need.

The framework matters because most bad technical documentation mixes modes. An API reference turns into a tutorial. A tutorial behaves like a reference manual. Pick the mode first; structure follows.

### The four modes

- **Tutorial** — teaches a beginner by walking through a complete learning path. Optimised for *progress and confidence*. Prerequisites, a realistic path, a finished outcome, "what to do next."
- **How-to guide** — helps a reader complete a specific task they already understand the need for. Optimised for *direct steps*. Task in the title, prerequisites, numbered steps, verification.
- **Reference** — lets the reader look up exact facts. Optimised for *completeness, consistency, and scanning*. Same shape per entry. Required vs optional parameters. Defaults, return values, error cases. No long conceptual explanations — link out instead.
- **Explanation** — helps the reader understand a concept, tradeoff, or system. Optimised for *mental models*. Start with the question the explanation answers. Define concepts before using them. Use examples and comparisons. Explain tradeoffs and reasons.

A README usually combines modes — that is fine — but each section inside it should still know which job it is doing.

### Picking the mode by reader question

| Reader's question | Mode |
|---|---|
| "How do I learn this from scratch?" | Tutorial |
| "How do I do this specific thing?" | How-to |
| "What are the exact details / parameters / fields?" | Reference |
| "Why does it work this way?" | Explanation |

When in doubt: ask what the reader will do with the page. Read it once and never return → tutorial or explanation. Return to look something up → reference. Follow it step-by-step now → how-to.

### README shape

A README is usually a compact mix. A flexible default order:

1. What this is (one or two sentences).
2. Who it is for (when not obvious).
3. Quick start (install, minimal usage).
4. Common usage (the 80% case).
5. Configuration / integration notes.
6. Troubleshooting.
7. Links to deeper docs (tutorial, how-to, reference, explanation).

A tiny library does not need every section. A large platform may need each of these to link out to a full page.

## Cross-cutting structural choices

A few decisions that apply to any pattern above.

### When to use headings vs paragraphs

Headings break a document into navigable sections. Use them when:

- The document is long enough that readers need to find specific parts.
- Sections cover distinct topics, not just successive paragraphs on the same topic.
- The reader will return to the document and need to re-locate something.

Do not use headings to break up a short flowing argument. Two-paragraph sections with their own H3 headings make the document feel choppy and bureaucratic.

### When a list beats prose

Use a list when:

- The items are genuinely parallel (same kind of thing).
- The order does not carry meaning (or the list is numbered specifically because order matters).
- The reader will scan rather than read straight through.

Do not list things that have natural prose connectives between them ("first… then… because… therefore…"). Prose carries the relationship; a list flattens it.

### Section breaks within a section

A section break (extra blank line, horizontal rule, or `***`) signals "we are shifting topic or perspective without starting a new section." Useful in long-form writing to mark a beat change without the heavy formatting of a heading.

Most technical and business writing does not need these. Use them in essays, long-form articles, and reports.

## Picking the right pattern

Quick guide:

- Memo, status update, decision doc → **BLUF**
- Announcement, news, release notes, incident report → **Inverted pyramid**
- Persuasive paragraph or argument within a larger doc → **PREP**
- Analysis or strategy doc that needs to set up *why* the question matters → **SCQA**
- Essay, blog post, narrative non-fiction → **Lead / body / close**
- Technical documentation → pick a **Diataxis mode** first (tutorial / how-to / reference / explanation), then structure within that. READMEs use a compact mix; see the README shape section above.

For audience-driven choices between patterns, see `audience-awareness`.

## Related skills

- `audience-awareness` — which structure fits which reader and document type.
- `writing-clearly-and-concisely` — sentence-level polish within each section.
- `de-slop` — remove AI patterns from prose once the structure is right.
- `tech-doc-templates` — RFC and ADR templates that bake structure into the document type.
