# Writing Toolkit Licensing

The `writing-toolkit` plugin wrapper and its original skill content are MIT-licensed (see the plugin's `LICENSE` file at the repository root). Some skills incorporate adapted material from upstream sources under different licences, listed below.

If you are distributing the plugin or content derived from it, follow the upstream licence for each adapted component.

## MIT-licensed (plugin wrapper and original content)

- `.claude-plugin/plugin.json`
- `skills/writing-clearly-and-concisely/SKILL.md` (original commentary and structure; the `elements-of-style.md` reference is public domain — see below)
- `skills/audience-awareness/SKILL.md`
- `skills/document-structure/SKILL.md`
- `skills/tech-doc-templates/SKILL.md` and the two template files under `templates/`

## Public domain

- `skills/writing-clearly-and-concisely/elements-of-style.md` — *The Elements of Style* by William Strunk Jr. (1918). Sourced from [Project Gutenberg #37134](https://www.gutenberg.org/files/37134/37134-h/37134-h.htm). No licence obligations.

## Multi-licensed: `skills/de-slop/`

The `de-slop` skill consolidates content from two upstream sources, each under a different licence. See `skills/de-slop/LICENSE-UPSTREAM` for the full upstream licence text and attribution.

- **Flutter Authors' "Rules for Natural Writing"** — reproduced under its original BSD-style licence.
- **Wikipedia's ["Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)** — available under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) and the [GNU Free Documentation License](https://www.gnu.org/licenses/fdl-1.3.html). Content derived from this source carries the same dual licence in this plugin. Attribution is given to the contributors of the Wikipedia article and to WikiProject AI Cleanup.

## Notes for redistributors

- The `plugin.json` `license` field is set to `MIT`. That reflects the licence of the plugin wrapper and original content; it does **not** override the upstream obligations on adapted material in `skills/de-slop/` or the public-domain status of `elements-of-style.md`.
- If you reuse `de-slop` content separately from this plugin, preserve the attribution shown in `skills/de-slop/LICENSE-UPSTREAM` and apply the appropriate upstream licence.
