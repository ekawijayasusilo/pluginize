# writing-toolkit

Skills for writing high-quality, human-readable documents: sentence-level clarity, AI-slop removal, audience awareness, document structure, and technical-doc templates (RFC, ADR). The skills cross-reference each other and are designed to be layered — load the one that matches your problem and it points you to the rest.

## Skills

- **writing-clearly-and-concisely** — sentence-level polish using Strunk's *Elements of Style*: tighten sentences, fix grammar and punctuation, cut needless words. Triggers when editing prose for clarity at the sentence and paragraph level.
- **de-slop** — strip AI-writing tells (puffery, rule-of-three, em-dash overuse, chatbot artifacts) so prose reads as human-written. Triggers when editing or reviewing prose, especially AI-assisted drafts.
- **audience-awareness** — identify the reader and document type first, since the other skills' rules shift by audience (a technical doc, a launch post, and an essay each want different things). Triggers when starting a piece or sanity-checking which conventions apply.
- **document-structure** — organize whole documents with established patterns: BLUF, inverted pyramid, PREP, SCQA, and the Diataxis modes for technical docs. Triggers when the document's organization is the problem, not the sentences.
- **tech-doc-templates** — scaffold an RFC or ADR from a sensible-default template. Triggers when starting one of those documents from scratch.

## How the skills fit together

Most writing tasks use more than one. A typical flow: pick the structure (`document-structure` or `tech-doc-templates`), calibrate to the reader (`audience-awareness`), draft, then polish (`writing-clearly-and-concisely` with `de-slop`). Each skill links to its siblings, so loading one surfaces the others.

## Installation

Load this plugin via your Claude Code marketplace configuration, or point Claude Code at the `plugins/writing-toolkit/` directory directly (it ships its own `.claude-plugin/plugin.json` manifest).

## Licensing and attribution

The plugin wrapper and original skill content are MIT-licensed. Some skills adapt upstream material under other licences — *The Elements of Style* (public domain), the Flutter Authors' "Rules for Natural Writing", and Wikipedia's "Signs of AI writing". See [LICENSES.md](LICENSES.md) for the full breakdown and redistribution obligations.
