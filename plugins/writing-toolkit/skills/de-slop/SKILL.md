---
name: de-slop
description: Remove AI-writing patterns (slop) from prose so it reads as natural, human-written text. Use when editing or reviewing prose — especially anything drafted with AI help — to strip puffery, vague attributions, em-dash overuse, banned-word habits, rule-of-three formulas, copula avoidance, chatbot artifacts, and other tells. Pairs with writing-clearly-and-concisely for sentence-level polish.
---

# De-Slop: Remove AI Writing Patterns

This skill helps you edit prose so it does not read as AI-generated. It consolidates two bodies of guidance: rules for natural writing (from the Flutter team) and Wikipedia's "Signs of AI writing" catalogue (maintained by WikiProject AI Cleanup).

## Your task

When given text to de-slop:

1. Identify AI patterns from the catalogue below.
2. Rewrite problematic sections in place.
3. Preserve meaning. Match the intended tone (formal, technical, casual).
4. **Do not invent specificity** to fill the gap left by removed puffery. See the Factual safety rule below.
5. Do not "improve" beyond removing slop — this skill is for cleanup, not voice injection.
6. Run the self-audit checklist at the end before declaring done.
7. Run a final adversarial pass: ask yourself "what about this still reads as AI-generated?" Note remaining tells. Revise.

## Factual safety rule

This is the most important rule in this skill. Read it before applying any other pattern.

Removing AI puffery often leaves a gap. The temptation is to fill the gap with concrete details — dates, named organisations, specific numbers, causal explanations. **Do not do this unless those details are present in the source text, the user's supplied context, cited sources, or files you have been asked to inspect.** Concrete language is not a license to add new facts.

A clear sentence with unsupported details is worse than a vague sentence. At least the vague sentence does not lie.

When the source does not support a concrete claim, you have three valid options:

1. **Remove** the unsupported claim entirely.
2. **Narrow** the claim to what the source actually supports.
3. **Mark** the gap with `[citation needed]` or `[verify: ...]` so the writer can fill it in.

The examples in this skill show what good rewrites look like *assuming the writer has the relevant facts*. If you apply this skill without source material, prefer the conservative path (remove or narrow). Do not invent.

A useful self-check after rewriting: scan the rewrite for any new date, number, named organisation, named tool, location detail, causal explanation, or superlative. For each one, ask: was it in the source? If not, remove or mark it.

This skill is for clarity and reader trust. It is not a tool for evading AI detectors. Do not make edits that reduce accuracy, attribution, or transparency just to make text appear less AI-generated.

## When to use this skill

Use this skill whenever prose may carry AI tells:

- Editing AI-generated drafts before publishing them
- Reviewing your own writing if it has started to sound generated
- Cleaning up text pasted from a chat assistant into a longer document

For sentence-level grammar, conciseness, and clarity, pair this skill with `writing-clearly-and-concisely`. For audience-specific application of these rules, see `audience-awareness`.

## Voice calibration (optional)

If the user provides a writing sample (their own prior writing), analyse it before rewriting:

1. Read the sample. Note sentence-length patterns, word-choice level, paragraph openings, punctuation habits, recurring phrases, transition style.
2. Match those patterns in the rewrite. Do not just strip AI markers — replace them with patterns from the sample.
3. When no sample is provided, fall back to neutral, varied prose that fits the document's genre.

How the user provides a sample:

- Inline: "De-slop this text. Here's a sample of my writing for voice matching: [sample]"
- File: "De-slop this text. Use my writing style from [file path] as a reference."

## Content patterns

### 1. Undue emphasis on significance, legacy, and broader trends

Words to watch: *stands/serves as, is a testament/reminder, a vital/significant/crucial/pivotal/key role/moment, underscores/highlights its importance, reflects broader, symbolising its ongoing/enduring/lasting, contributing to the, setting the stage for, marking/shaping the, represents/marks a shift, evolving landscape, focal point, indelible mark, deeply rooted*

LLM writing puffs up importance with statements about how arbitrary aspects represent or contribute to a broader topic. If a subject matters, the facts should show it.

Before: *The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. This initiative was part of a broader movement across Spain to decentralise administrative functions.*

After: *The Statistical Institute of Catalonia was established in 1989 to collect and publish regional statistics independently from Spain's national statistics office.*

### 2. Superficial analyses with -ing endings

Words to watch: *highlighting, underscoring, emphasising, ensuring, reflecting, symbolising, contributing to, cultivating, fostering, encompassing, showcasing*

AI tacks present-participle phrases onto sentences to add fake depth. Delete the dangling clause if it just restates or adds vague commentary.

Before: *The temple's colour palette of blue, green, and gold resonates with the region's natural beauty, symbolising Texas bluebonnets, the Gulf of Mexico, and the diverse Texan landscapes, reflecting the community's deep connection to the land.*

After: *The temple uses blue, green, and gold. The architect chose these colours to reference local bluebonnets and the Gulf coast.*

### 3. Promotional and advertisement-like language

Words to watch: *boasts a, vibrant, rich (figurative), profound, enhancing its, showcasing, exemplifies, commitment to, natural beauty, nestled, in the heart of, groundbreaking (figurative), renowned, breathtaking, must-visit, stunning*

LLMs drift toward "cultural heritage" rhetoric even in neutral contexts. Keep tone factual.

Before: *Nestled within the breathtaking region of Gonder in Ethiopia, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage and stunning natural beauty.*

After (with source material that mentions a market and a church): *Alamata Raya Kobo is a town in the Gonder region of Ethiopia, known for its weekly market and 18th-century church.*

### 4. Vague attributions and weasel words

Words to watch: *industry reports, observers have cited, experts argue, some critics argue, several sources / publications (when few are cited)*

Attribute opinions to specific people or sources, or do not attribute them at all.

Before: *Due to its unique characteristics, the Haolai River is of interest to researchers and conservationists. Experts believe it plays a crucial role in the regional ecosystem.*

After (assuming source material like *"2019 Chinese Academy of Sciences survey: 7 endemic fish species"*): *The Haolai River supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences.*

### 5. Outline-like "Challenges and Future Prospects" sections

Words to watch: *Despite its... faces several challenges..., Despite these challenges, Challenges and Legacy, Future Outlook*

Many LLM-generated articles end with a formulaic "Challenges" or "Future" section that contains no real content. Cut it. End with the last concrete fact.

Before: *Despite its industrial prosperity, Korattur faces challenges typical of urban areas, including traffic congestion and water scarcity. Despite these challenges, with its strategic location and ongoing initiatives, Korattur continues to thrive as an integral part of Chennai's growth.*

After (no additional source material): *Traffic congestion and water scarcity are recurring problems in Korattur.*

After (with source material giving dates and projects): *Traffic congestion increased after 2015 when three new IT parks opened. The municipal corporation began a stormwater drainage project in 2022 to address recurring floods.*

The "challenges" formula needs to be cut either way — but the dates and named projects must come from the source, not from the rewrite.

### 6. Generic positive conclusions

Vague upbeat endings ("the future looks bright," "exciting times lie ahead," "a major step in the right direction") add nothing. End on a concrete fact or the last substantive point.

### 7. Persuasive authority tropes

Phrases to watch: *the real question is, at its core, in reality, what really matters, fundamentally, the deeper issue, the heart of the matter*

These pretend to cut through noise to a deeper truth, but the sentence that follows usually just restates an ordinary point with extra ceremony.

Before: *The real question is whether teams can adapt. At its core, what really matters is organisational readiness.*

After: *The question is whether teams can adapt. That mostly depends on whether the organisation is ready to change its habits.*

### 8. Signposting and announcements

Phrases to watch: *let's dive in, let's explore, let's break this down, here's what you need to know, now let's look at, without further ado*

LLMs announce what they are about to do instead of doing it. Cut the announcement and start with the content.

Before: *Let's dive into how caching works in Next.js. Here's what you need to know.*

After: *Next.js caches data at multiple layers: request memoization, the data cache, and the router cache.*

## Language and grammar patterns

### 9. Overused AI vocabulary

High-frequency AI words: *actually, additionally, align with, crucial, delve, emphasising, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate / intricacies, key (adjective), landscape (abstract), pivotal, showcase, tapestry (abstract), testament, underscore (verb), valuable, vibrant.*

These words appear far more frequently in post-2023 text and often co-occur. They are **statistically overused, not banned.** Each has legitimate uses — but if you find several in one paragraph, simplify.

Before: *Additionally, a distinctive feature of Somali cuisine is the incorporation of camel meat. An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.*

After: *Somali cuisine also includes camel meat, considered a delicacy. Pasta dishes, introduced during Italian colonisation, remain common, especially in the south.*

### 10. Copula avoidance

Words to watch: *serves as / stands as / marks / represents [a], boasts / features / offers [a]*

LLMs substitute elaborate constructions for simple is/are/has. Use the simple form unless the elaborate verb actually means something different.

Before: *Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces and boasts over 3,000 square feet.*

After: *Gallery 825 is LAAA's exhibition space for contemporary art. It has four rooms totalling 3,000 square feet.*

### 11. Negative parallelisms and tailing negations

Constructions like "Not only...but..." or "It's not just X; it's Y" are overused. Same for clipped tailing negations such as "no guessing" or "no wasted motion" tacked onto a sentence.

Before: *It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere. It's not merely a song, it's a statement.*

After: *The heavy beat adds to the aggressive tone.*

Before (tailing negation): *The options come from the selected item, no guessing.*

After: *The options come from the selected item without forcing the user to guess.*

### 12. Rule of three

LLMs force ideas into groups of three to sound comprehensive. Use a third item only if it is a real third item.

Before: *The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights.*

After: *The event includes talks and panels, with time for informal networking between sessions.*

### 13. Elegant variation (synonym cycling)

AI has repetition-penalty code that causes excessive synonym substitution ("the protagonist" → "the main character" → "the central figure" → "the hero"). Repeat the name, or use a pronoun.

Before: *The protagonist faces many challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home.*

After: *The protagonist faces many challenges, eventually triumphs, and returns home.*

### 14. False ranges

Avoid "from X to Y" unless X and Y are the endpoints of a meaningful scale (time, size, etc.). Two random topics are not a range.

Before: *Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.*

After: *The book covers the Big Bang, star formation, and current theories about dark matter.*

### 15. Passive voice and subjectless fragments — applied with judgment

LLMs often hide the actor or drop the subject. Rewrite to active voice when the sentence becomes clearer.

Important: not every sentence fragment is slop. Technical writing legitimately uses short imperative fragments ("Run the script. Check the output.") and compressed forms ("Returns null if not found."). The rule applies to passive constructions that genuinely obscure the actor in prose contexts, not to deliberate technical-writing brevity.

Before (passive, agent matters): *The decision was made to discontinue the legacy API in Q3.*

After: *The platform team decided to discontinue the legacy API in Q3.*

### 16. Excessive hedging

Over-qualifying statements ("could potentially possibly," "might have some effect") signals uncertainty about everything.

Note the genre exception: hedging is correct in academic and scientific writing where overclaiming is the actual problem. The rule targets vague hedging in general prose.

Before: *It could potentially possibly be argued that the policy might have some effect on outcomes.*

After: *The policy may affect outcomes.*

### 17. Filler phrases

Common bloat → tighter form:

- "In order to achieve this goal" → "To achieve this"
- "Due to the fact that it was raining" → "Because it was raining"
- "At this point in time" → "Now"
- "In the event that you need help" → "If you need help"
- "The system has the ability to process" → "The system can process"
- "It is important to note that the data shows" → "The data shows"

### 18. Banned temporal words in code and comments

Do not use relative temporal terms in code, variable names, function names, or comments. They lose meaning as the codebase ages.

Banned: *now, currently, existing behavior, previous behavior, old, new, modern.*

Bad: `// This function now uses the config parser instead of hardcoding.`

Good: `// Resolves paths via ConfigParser.loadConfig to support custom config locations.`

This rule applies to code and code comments specifically. Prose can still say "currently" when it genuinely means "as of writing."

## Style and formatting patterns

### 19. Em dash overuse

LLMs use em dashes (—) more than humans, mimicking "punchy" sales writing. Most can be rewritten more cleanly with commas, periods, or parentheses.

Before: *The term is primarily promoted by Dutch institutions—not by the people themselves. You don't say "Netherlands, Europe" as an address—yet this mislabeling continues—even in official documents.*

After: *The term is primarily promoted by Dutch institutions, not by the people themselves. You don't say "Netherlands, Europe" as an address, yet this mislabeling continues in official documents.*

### 20. Overuse of boldface

AI emphasises phrases in boldface mechanically. Bold should mark genuine emphasis, not "this is a keyword."

Before: *It blends **OKRs (Objectives and Key Results)**, **KPIs (Key Performance Indicators)**, and visual strategy tools such as the **Business Model Canvas (BMC)** and **Balanced Scorecard (BSC)**.*

After: *It blends OKRs, KPIs, and visual strategy tools like the Business Model Canvas and Balanced Scorecard.*

### 21. Inline-header vertical lists

AI outputs lists where each item starts with a bolded header followed by a colon. Use prose or simple bullets.

Before:

```
- **User Experience:** The user experience has been significantly improved with a new interface.
- **Performance:** Performance has been enhanced through optimised algorithms.
- **Security:** Security has been strengthened with end-to-end encryption.
```

After: *The update improves the interface, speeds up load times through optimised algorithms, and adds end-to-end encryption.*

### 22. Title case in headings

AI capitalises every main word in headings. Use sentence case — capitalise the first word and proper nouns only.

Before: `## Strategic Negotiations And Global Partnerships`

After: `## Strategic negotiations and global partnerships`

### 23. Emojis — scoped

Do not decorate headings or bullet points with emojis in formal or long-form prose (essays, reports, formal documentation, academic writing).

Carve-outs where emojis are conventional and fine:

- PR descriptions and commit messages (✅ ❌ 🚧 as status markers)
- READMEs and changelogs that already use them as a house style
- Internal Slack updates and status posts
- LinkedIn / blog posts where they match the author's voice

The rule targets emojis used as visual filler, not emojis that convey real information in their native context.

Before (formal report): *🚀 **Launch Phase:** The product launches in Q3 / 💡 **Key Insight:** Users prefer simplicity / ✅ **Next Steps:** Schedule follow-up meeting*

After: *The product launches in Q3. User research showed a preference for simplicity. Next step: schedule a follow-up meeting.*

### 24. Curly vs straight quotation marks — scoped

In code, Markdown, plaintext, and most technical contexts, use straight quotes (`"`, `'`). LLMs often output curly quotes ("...") that break code blocks and look out of place in source files.

In typeset prose (books, magazines, formatted long-form writing), curly quotes are correct. The rule targets curly quotes leaking into source-file contexts where straight quotes are expected.

### 25. Fragmented headers

A heading followed by a one-line paragraph that just restates the heading before the real content begins. Cut the restatement.

Before:

```
## Performance

Speed matters.

When users hit a slow page, they leave.
```

After:

```
## Performance

When users hit a slow page, they leave.
```

## Communication patterns (chat artifacts in pasted text)

### 26. Collaborative communication artifacts

Words to watch: *I hope this helps, Of course!, Certainly!, You're absolutely right!, Would you like..., let me know, here is a...*

Text meant as chatbot correspondence gets pasted into documents. Strip it.

Before: *Here is an overview of the French Revolution. I hope this helps! Let me know if you'd like me to expand on any section.*

After: *The French Revolution began in 1789 when financial crisis and food shortages led to widespread unrest.*

### 27. Knowledge-cutoff disclaimers

Phrases to watch: *as of [date], up to my last training update, while specific details are limited / scarce..., based on available information...*

AI disclaimers about incomplete information get left in pasted text. Either cite a real source or just state the fact.

Before: *While specific details about the company's founding are not extensively documented in readily available sources, it appears to have been established sometime in the 1990s.*

After: *The company was founded in 1994, according to its registration documents.*

### 28. Sycophantic tone

Overly positive, people-pleasing language belongs in a chat reply, not a document.

Before: *Great question! You're absolutely right that this is a complex topic. That's an excellent point about the economic factors.*

After: *The economic factors you mentioned are relevant here.*

## Longer before/after passages

Single-rule examples show patterns in isolation. Real prose carries several at once.

### Example A — significance puffery, copula avoidance, -ing dangling, rule of three, em dash

Before:

> The introduction of containerisation marked a pivotal moment in the evolution of software deployment, representing a fundamental shift in how engineering teams ship, scale, and operate their systems. At its core, Docker serves as a packaging mechanism — one that has enduring influence across the industry — fostering a vibrant ecosystem of orchestrators, registries, and runtimes. It is not just a tool; it is a foundation. By standardising the runtime environment, Docker enabled a new wave of practices, transforming how developers think about portability, reproducibility, and operational consistency.

After:

> Docker, released in 2013, packages an application with its dependencies into a runnable image. Teams adopted it because the same image runs on a developer laptop and a production server. That shifted how applications are shipped: a build artifact became a container image, and the gap between development and production environments narrowed. Kubernetes, Nomad, and other orchestrators were built to schedule and manage these images at scale.

### Example B — chatbot artifact, hedging, vague attribution, generic conclusion

Before:

> Great question! Based on available information, it could potentially be argued that adopting feature flags might have several benefits for engineering teams. Industry observers have noted that this practice continues to grow in popularity. Despite some challenges related to operational complexity, the future of feature-flagging looks bright. Let me know if you'd like me to expand on any of these points!

After:

> Feature flags let teams ship code without making it visible to users. The cost is operational: stale flags accumulate and the codebase ends up carrying many half-completed migrations. Teams that use flags well treat each one as having an expected lifetime and audit them on a schedule. LaunchDarkly, Flipper, and Unleash are common managed and self-hosted options.

## The full process

1. Read the input text.
2. Identify all instances of the patterns above.
3. Rewrite each problematic section. Preserve meaning. Match the document's tone.
4. **Run the factual-safety pass.** For every newly concrete claim in the rewrite (any date, number, named organisation, named tool, location detail, causal explanation, or superlative), verify it was in the source. Remove, narrow, or mark anything invented.
5. Run the self-audit checklist below.
6. Ask: "What about this still reads as obviously AI-generated?" Note remaining tells in a sentence or two.
7. Revise once more to remove those.
8. Return: final rewrite + (optional) a brief summary of changes.

## Plain-language self-audit checklist

Before declaring the rewrite done, audit it on the metrics below. These are the things the model can reliably check from the text alone. They will not catch every issue, but a passage that fails several of these will read as AI-generated even if no single rule above was violated.

**Sentence length**

- Average words per sentence — count words across all sentences and divide. Target ~15-20 for general prose; longer is acceptable for academic or technical writing, shorter for marketing or hype copy.
- Sentence-length variance — if every sentence falls within ±3 words of the average, the prose has a robotic rhythm. Real human writing varies. Aim for a mix of short (5-10 words), medium (12-20), and occasional longer sentences (25+).

**Passive constructions**

- Count sentences in passive voice. A rough proportion above ~25% in general prose suggests overuse. Scientific/legal writing legitimately runs higher.

**Adverb density**

- Count -ly adverbs. Many is a flag. Often a precise verb beats verb + adverb ("walked slowly" → "trudged"; "said angrily" → "snapped").

**Repeated openers**

- Look at the first 2-3 words of every sentence. If many sentences start with the same word or construction (every paragraph opening with "Additionally," "Furthermore," "In addition"), vary them.

**Paragraph length**

- All paragraphs roughly the same length signals AI patterning. Real writing has paragraphs of varied length depending on what each one is doing.

**Factual safety**

- Scan the rewrite for new dates, numbers, named organisations, named tools, locations, or causal claims that were not in the source. For each one, ask: did this come from the source? If not, remove it, narrow it, or mark it with `[verify: ...]`. A clean-sounding rewrite that invents specificity is a worse output than a slightly vague one.

### Limitations of this checklist

This skill cannot compute Flesch-Kincaid, Gunning Fog, or true lexical-diversity scores without a real computation tool. The checks above are the ones a language model can apply reliably from text alone. For deeper readability analysis, a separate analyser tool (script, MCP server) would be needed.

## Related skills

For complementary guidance, also load:

- `writing-clearly-and-concisely` — sentence-level grammar, conciseness, and mechanics (Strunk). Use together with this skill when editing prose.
- `audience-awareness` — adjusts which of these rules apply most strongly to which audience.

## Attribution

This skill consolidates two upstream sources:

- The Flutter Authors' "Rules for Natural Writing" (2026, BSD-style licence — see `LICENSE-UPSTREAM`).
- Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup.
