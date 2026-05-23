---
name: prompt-engineering
description: Use when refining, polishing, or rewriting an input prompt to improve LLM output quality, consistency, or structure. Triggers on requests like "improve this prompt", "why isn't this prompt working", "help refine this prompt", "make this prompt better", or converting vague instructions into structured prompts. Covers XML structuring, few-shot examples, output format specification, instruction clarity, and degrees-of-freedom calibration. Do NOT trigger for general LLM/API questions or runtime configuration (caching, thinking budgets, stop sequences).
---

# Prompt Engineering

Practical techniques for refining input prompts so they produce more consistent, accurate, and useful LLM outputs.

## When to use this skill

**Trigger on:**

- "Improve this prompt"
- "Why isn't this prompt working?"
- "Make this prompt better"
- "Help refine this prompt"
- "Convert this vague instruction into a structured prompt"
- A prompt that produces inconsistent or wrong-format output

**Do NOT trigger on:**

- General questions about how LLMs work
- API/SDK configuration (caching, stop sequences, temperature, thinking budgets)
- Designing agent instructions, hooks, or commands (different skill)

## Core techniques

### 1. Structure with XML tags

Wrap distinct content types in descriptive XML tags so the model can parse them unambiguously. This is the single highest-leverage change for most prompts.

Common tags: `<instructions>`, `<context>`, `<examples>`, `<input>`, `<output_format>`.

**Example:**

```xml
<instructions>
Classify the support ticket below by issue type and urgency.
</instructions>

<output_format>
JSON with keys: issue_type, urgency (low/medium/high), summary.
</output_format>

<input>
My login doesn't work and I keep getting error 403.
</input>
```

Place long documents (large reference material, source files) ABOVE the query, not below — this ordering produces measurably better results.

### 2. Few-shot examples

Show 2–5 input/output pairs that demonstrate the desired pattern. Examples are more effective than describing the pattern in prose.

```xml
<examples>
  <example>
    <input>Login fails with error 403</input>
    <output>{"issue": "authentication", "urgency": "high"}</output>
  </example>
  <example>
    <input>Add dark mode please</input>
    <output>{"issue": "feature_request", "urgency": "low"}</output>
  </example>
</examples>

<input>Can't upload files larger than 10MB, getting timeout</input>
```

Use when consistent format matters, edge cases need handling, or prose instructions aren't producing reliable results.

### 3. Set degrees of freedom

Match instruction specificity to how fragile the task is. Think of the model as a robot exploring a path:

**Narrow bridge with cliffs (low freedom)** — operations are fragile, sequence matters, one approach is correct. Give exact scripts and forbid modification.

```text
Run exactly:
python scripts/migrate.py --verify --backup

Do not modify the command or add flags.
```

**Path through a forest (medium freedom)** — a preferred pattern exists but some variation is fine. Give a template with parameters.

```text
Use this report template; customize sections per audience:
- Executive summary (2–3 sentences)
- Findings (bullets)
- Recommendations (numbered)
```

**Open field (high freedom)** — many approaches work, context decides the best one. Give general direction and trust the model.

```text
Review this code. Identify bugs, suggest improvements,
and check adherence to project conventions.
```

### 4. Output format specification

State the expected output structure explicitly. Modern AI models tend to be more literal in following instructions — if you want a behavior applied to *every* section, say so explicitly ("apply this to every section, not just the first").

Specify: schema (for structured output), length bounds, required fields, formatting rules, and what to do when information is missing.

## Output formatting: HTML for documents

When the prompt asks the model to *generate* a document, plan, report, or interactive view, instruct it to produce **HTML output** rather than Markdown. Modern AI models render interactive elements, tables, SVG, and CSS-styled layouts well, and the result is more useful and shareable.

Reference: [The Unreasonable Effectiveness of HTML](https://claude.com/blog/using-claude-code-the-unreasonable-effectiveness-of-html).

Note: this is about what the model *outputs*. The prompt you *send* should still use XML tags for structure.

## Progressive disclosure when iterating

Don't start with a maximally complex prompt. Layer in only what's needed:

1. **Direct instruction** — "Summarize this article"
2. **Add constraints** — "Summarize in 3 bullet points, focusing on findings"
3. **Add reasoning** — "Identify the main findings, then summarize each"
4. **Add examples** — Include 2–3 input/output pairs

Move to the next level only when the current one fails on real inputs.

## Best practices

- **Be specific.** Vague prompts produce inconsistent results.
- **Show, don't tell.** Examples beat descriptions.
- **Change one thing at a time.** When refining, isolate which change made the difference.
- **Stay concise.** Modern AI models support large context windows (hundreds of thousands to over a million tokens depending on model), but each token competes with other content sharing the window — every token should earn its place.
- **Match style to fragility.** Use low / medium / high freedom appropriately.

## Common pitfalls

- **Over-engineering** — Starting with a complex prompt before trying a simple one.
- **Example pollution** — Few-shot examples that don't match the target task confuse the model.
- **Ambiguous instructions** — Leaving room for multiple interpretations.
- **Ignoring edge cases** — Not testing on unusual or boundary inputs.
- **Adding "think step by step" to reasoning models** — Redundant when the model already reasons natively; clutters the prompt and can push reasoning into the user-visible output.
- **Reaching for runtime knobs** — Caching, thinking budgets, and stop sequences are *not* the fix when the prompt text is what's failing.
