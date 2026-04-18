# deundeslop

A style-only self-edit pass for stripping AI tells from LLM-generated prose — without damaging meaning, facts, voice, terminology, or list items.

Built from real experience generating TV reviews for [TheAttReviews.com](https://theattreviews.com) and refined there over months. The process works in general, but the banned-vocabulary list reflects prestige-TV-review context. Swap the word list for your domain; the structural rules and the overriding principle carry over intact.

## Why "deundeslop"?

A daft joke. The workflow is Sub-pass A → Sub-pass B → Sub-pass A:

- **Deslop** — Sub-pass A, strips the AI fingerprints (em dashes, "delve", "at its core", banned vocab, etc.)
- **Undeslop** — Sub-pass B, restructures prose for burstiness and paragraph shape (which sometimes reintroduces small slop as a side-effect)
- **Deundeslop** — Sub-pass A runs again, catching anything the restructure reintroduced

deslop (slop-free) → undeslop (back to slop) → deundeslop (slop-free again). The three-pass structure is the whole point, and the repo name is a nod to it.

## What's in this repo

| File | For |
|---|---|
| `guide.md` | Any LLM. Paste as a system prompt or reference document. Plain markdown, no frontmatter. |
| `.claude/agents/deundeslop.md` | Claude Code users who want an isolated sub-agent. Drop-in agent file. Invoked via the Task tool with `subagent_type: "deundeslop"`. |
| `.claude/skills/deundeslop/SKILL.md` | Claude Code users who want a slash command. Drop-in skill. Invoked via `/deundeslop` or auto-triggered when Claude detects a de-slop request in context. |

All three files contain the same rules and the same three-pass process. The Claude versions add frontmatter and invocation framing; the generic version is portable.

**Agent vs skill — which to use?**
- **Agent** runs the workflow in an isolated sub-session and returns a report to the main conversation. Good when you want a clean hand-off and a standalone audit trail.
- **Skill** loads the rules into the current conversation's context and runs in-line. Feels like a slash command. Good when you're already in a conversation about the text and want the rewrite to happen right there.

## The overriding principle — FIRST, DO NO HARM

Every rule in this repo is subordinate to this principle. It is better to leave a residual AI tell in place than to:

- Invent a first-person memory or viewer/reader experience that was not in the source
- Reallocate or drop a descriptor attached to the subject
- Translate domain-specific terminology, slang, or idioms into generic English
- Drop quantifiers, hedges, or contrastive conjunctions ("but", "a lot", "or even really", "almost", "arguably")
- "Improve" a sentence in ways that shift meaning
- Fix a grammar quirk that was a deliberate voice choice
- Drop a list item

When in doubt, keep the original and flag it in the report for the user to decide. A clean-scoring rewrite with a fabricated memory is a failed rewrite.

## How it works (short version)

1. **Sub-pass A — mechanical scan.** 18 regex patterns catch em dashes, smart quotes, banned vocab (delve, tapestry, navigate, resonate, etc.), banned phrases ("not just X it's Y", "at its core", "stands as"), banned praise compounds (razor sharp, pitch-perfect, unspools, tour de force).

2. **Sub-pass B — structural rewrite.** 6 checks for sentence-length variation (burstiness), parallel copula stacks (3+ consecutive "X is Y" sentences), paragraph shape (topic → 3 supports → summary template), opening formulas, first-person handling with a strict rewrite-mode inversion, and one deliberate imperfection.

3. **Sub-pass A re-run.** Rewrites sometimes reintroduce slop. A final terminal grep catches it before you ship.

See `guide.md` for the full rules, checklist, regex table, and examples.

## Origin — TheAttReviews

I generate reviews and show descriptions for my site using Claude as an author-in-the-loop. The first iterations read exactly like the AI-generated content Google's classifiers are trained to flag: em dashes on every line, "delves into" three times a paragraph, tricolons of evenly-weighted praise, "It's not just a drama — it's a mirror."

Three rounds of rule-tuning got me here:

1. First I banned the words. Minor improvement. Detectors still scored high because the rhythm was unchanged.
2. Then I added structural rules (burstiness, paragraph shape, parallel copula stacks). Bigger improvement.
3. Then I added FIRST, DO NO HARM after the agent started inventing reviewer memories ("I argued with Amanda by episode two") and reallocating genre descriptors ("a modern gangster drama" got moved off the show I was reviewing onto the comparison shows). That was the real breakthrough — the de-AI pass has to be subordinate to meaning preservation. Clean detector score plus fabricated content is a failed rewrite, not a successful one.

This repo is a one-time snapshot of that process as it stands today. TheAttReviews' own agent keeps evolving, and I'll occasionally sync significant updates back here.

## Usage

### Any LLM

Paste `guide.md` at the top of your conversation, then ask for a de-slop pass on your text. Instruct the model to follow FIRST, DO NO HARM and to include a report of what it changed and what it deliberately left.

### Claude Code

Copy `.claude/agents/deundeslop.md` into your own project's `.claude/agents/` directory. Then invoke the agent on any passage:

```
Use the deundeslop agent to de-slop this text: [paste]
```

Or point it at a file:

```
Use the deundeslop agent on src/content/my-article.md
```

The agent will run the three-pass workflow and return both the rewritten text and a transparent report of what it changed, what it left, and why.

## Contributing

Fork it, open a PR, or drop an issue. Particularly interested in:

- Domain-specific banned-vocab lists (medical, legal, crypto, games, technical docs)
- Patterns that DON'T move AI-detector scores (so the list can be trimmed, not just grown)
- Better structural-pass heuristics

## License

MIT. See `LICENSE`.
