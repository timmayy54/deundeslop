# Deundeslop — Guide

A style-only pass that strips AI tells from LLM-generated prose without damaging the content. Built from real experience generating TV reviews for TheAttReviews.com. Works in general; the banned-vocab list reflects prestige-TV-review context and you should extend or trim it for your own domain. The structural rules and the overriding principle generalise.

The name: Sub-pass A → Sub-pass B → Sub-pass A. Deslop (slop-free) → Undeslop (back to slop) → Deundeslop (slop-free again).

---

## FIRST, DO NO HARM (overriding principle)

Every rule below is SUBORDINATE to this principle. It is better to leave a residual AI tell in place than to do any of the following:

- **Invent a first-person memory or viewer / reader experience** that was not in the source. "I watched this over a weekend", "the finale broke me", "I kept rewinding the pilot", "my wife tapped out after two episodes" — FORBIDDEN when the original has no first-person source for them.
- **Change or reallocate a descriptor attached to the subject.** If the original calls the show "a modern gangster drama", that descriptor stays attached to the show, not reallocated to comparators.
- **Translate show-specific / domain-specific terminology, slang, or idioms into generic English.** "Frack" in *Battlestar Galactica* stays "frack". "Innie" / "outie" in *Severance* stays. Regional idioms like "not a bad shout", "taking the piss", "kitchen-table row" stay. If a word looks unusual, wrong, or like a typo, it is most likely a deliberate voice choice — do not rewrite it. When in doubt, keep verbatim and flag in the report.
- **Drop a quantifier, hedge, or contrastive conjunction.** Small words do meaningful work: "but", "yet", "although", "however" (contrasts); "a lot", "mostly", "largely", "nearly", "almost" (quantifiers); "or even really", "arguably", "roughly", "at times" (softeners); "very", "quite", "seriously" (intensifiers). Dropping them is a meaning change, not a style change.
- **"Improve" a sentence in ways that shift meaning, even subtly.** Rephrasing must preserve every claim, including tentative claims and hedged claims.
- **Fix a grammar quirk that was a deliberate voice choice.** Dialect, informal speech, working-class idiom, run-on-by-design sentences — usually intentional.
- **Drop a list item** (restated under the structural rules — the most common harm).

When in doubt, KEEP THE ORIGINAL. Flag the concern in the report. Every rule in this guide is SUBORDINATE to this principle. If applying a de-slop rule would damage meaning, terminology, a descriptor, a tone-word, a hedge, or voice, the rule does not apply and you keep the original.

The de-slop-ness of the final text is SECONDARY to the integrity of the original voice, meaning, and detail. A piece with 3 residual em dashes and full meaning is a better outcome than the same piece with 0 em dashes and a fabricated memory or a lost descriptor.

---

## Banned punctuation (zero tolerance in final output)

| Element | Status | Notes |
|---|---|---|
| Em dash `—` (U+2014) | BANNED | Use comma, full stop, colon, or parentheses |
| En dash `–` (U+2013) | BANNED | Use "to" for ranges, or hyphen |
| Figure dash `‒`, horizontal bar `―`, minus `−` | BANNED | |
| Non-breaking hyphen `‑` (U+2011) | BANNED | Only ASCII `-` (U+002D) |
| Smart / curly quotes `" " ' '` | BANNED | Straight `"` `'` only |
| Ellipsis char `…` (U+2026) | BANNED | Use `...` sparingly, ideally not at all |
| Semicolon `;` | STRONGLY DISCOURAGED | Max 1 per 1500-word piece |

### Em dash replacement table

| AI writes | Rewrite as |
|---|---|
| "Pierce Brosnan—usually dependable—sinks under..." | "Pierce Brosnan, usually dependable, sinks under..." |
| "It's not a masterpiece—but it's a good start" | "It's not a masterpiece. But it's a good start." |
| "—a scathing dissection of power" | ". A scathing dissection of power." |
| "—chief among them the inclusion of..." | ". Chief among them: the inclusion of..." |
| "something magnetic—Tom Hardy is the lifeblood" | "something magnetic. Tom Hardy is the lifeblood" |
| "woven into the fabric—emphasising unity" | "woven into the fabric, emphasising unity" |

---

## Banned vocabulary (detector fingerprints)

Strike on sight. Bracketed alternatives are suggestions, not a thesaurus — often the whole sentence should be reworked.

- **delve / delves / delving** [look at, dig into, get into, or cut]
- **tapestry** [mix, web, set — often cut the metaphor]
- **landscape** (figurative) [world, scene, or cut]
- **testament** ("a testament to") [proof, or cut]
- **navigate** (figurative) [deal with, work through]
- **resonate / resonates / resonant** [hit, land, stick]
- **nuanced / multifaceted / intricate** [complicated, layered, messy]
- **underscore / underscores** [shows, proves, or cut]
- **unparalleled / unprecedented / groundbreaking** [cut — almost always hype]
- **meticulous / meticulously** [careful, tight]
- **robust / seamless / holistic / cohesive** [cut or be specific]
- **pivotal / crucial / vital** [important, key, or be specific]
- **vibrant / rich** (as praise) [specific sensory word]
- **boasts** ("the show boasts a cast of...") [has]
- **nestled / steeped in** [in, set in]
- **showcases / showcasing** [shows]
- **leverages / leverage** [uses]
- **commitment to / dedication to** [just describe what they do]
- **journey** (figurative) [story, arc]
- **realm** [world, genre, or cut]

Adjust this list to your domain. These are the fingerprints for TV / film / culture-writing contexts. Medical, legal, technical, or game-review contexts will have their own set.

---

## Banned phrases (sentence-level constructions)

- **"It's not just X, it's Y"** and all variants ("It isn't merely X, it's Y", "More than just X, it's Y"). Single biggest detector tell. Zero tolerance.
- **"Not only X but also Y"** — replace with "X. And Y." or just "X and Y".
- **"Whether X or Y"** as balanced construction — one use per piece max.
- **"At its core / at its heart / at its best / at its worst"** — all four banned as opener formulas. Rewrite the claim directly.
- **"In today's world" / "In an era of" / "In the ever-evolving landscape of"** — banned openers.
- **"It's worth noting that / It's important to understand / It should be noted"** — hedging filler. Delete.
- **"This [subject] is..."** as repeated sentence opener — vary it.
- **"Stands as / serves as / marks / represents"** — AI copula avoidance. Use "is".
- **"Nothing short of" / "a masterclass in" / "a love letter to" / "a testament to"** — dead.
- **"Speaks to"** (figurative) — banned.
- **"Best described as"** — banned.
- **"Whether you're X or Y, this..."** — banned closer.

---

## Banned praise compounds

Multi-word praise modifiers and plot-progression verbs that slip past single-word greps.

- **razor sharp / razor-sharp** [sharp, cutting, precise, or be concrete]
- **pitch-perfect** [exactly right, on the nose, or cut]
- **career-defining / career-redefining** [cut the hype — be specific]
- **spot-on / dead-on** [right, exactly, or cut]
- **tour de force** [cut]
- **a masterstroke / a triumph** [cut]
- **unspools / unfurls** (as plot-progression verb) [unfolds, moves, builds]
- **crackles / crackling** (as praise) [cut the metaphor or be literal]
- **sings** ("the dialogue sings") [works, lands, hits]
- **visceral / searing / haunting** (as standalone praise) [be specific]
- **"one of the most X ever committed to screen / television / TV / film"** — cut the grandiose "ever" framing; make the claim directly.
- **"finest of its kind"** — cut.

---

## Banned structural patterns

- **Tricolon / rule of three** — no lists of three adjectives ("bold, distinctive, unforgettable"), no triple alliterative praise ("character, craft, and critique"), no triple parallel descriptors even when the items are internal links ("the grinding corporate dystopia of [Silo], the philosophical unease of [Westworld], or the technological anxiety of [Black Mirror]" IS a tricolon). One tricolon per piece maximum. When you break a tricolon, see Content preservation below — every item survives.
- **Content preservation when restructuring lists (HARD RULE, zero exceptions)** — when you break a tricolon, quadricolon, or any parallel-list construction, every item in the original MUST survive. "Paris, Milan, London, Glasgow" rewrites to 4 cities, not 3. "Too tall, fat, ugly and dumb" rewrites to 4 adjectives. Restructure SYNTAX (split across sentences, chain with "and…and…", convert to a bulleted list, reorder, interleave with connective tissue). NEVER drop items. If you cannot break the rhythm without dropping items, KEEP THE ORIGINAL LIST and flag in your report.
- **Balanced parallel sentences back-to-back** — if two consecutive sentences share the same clause rhythm ("The acting is sharp. The writing is sharper."), rewrite one.
- **Parallel copula stacks** — 3+ consecutive sentences of the form `[Subject] is [Y]` / `[Character]'s [X] is [Y]`. This is a signature AI move. Max 2 consecutive. Break with a question, a verb-led sentence, a fragment, or a concrete specific detail.
- **Topic sentence → 3 evenly weighted supports → closing restatement** — if a paragraph follows this template, break it. Cut the summary. Start mid-thought. Let the paragraph end on a specific detail, not a restated thesis.
- **Concluding rhetorical questions** — no.
- **Paragraph-end thesis restatement** — if the last sentence summarises the paragraph, cut it.

---

## Required: burstiness

Human writing has wide sentence-length variation. AI does not. Target:

- At least 3 sentences under 8 words per 500-word block.
- At least 1 sentence over 25 words per 500-word block.
- Never 3+ consecutive sentences of similar length (within 4 words of each other). Shorten one, expand another.
- Opening a paragraph with a 3-word sentence is fine. Do it sometimes.

Burstiness is the single biggest detector-score lever. Word-level swaps barely move scores; structural variation moves them a lot.

---

## Required: first-person voice (with the critical rewrite-mode inversion)

**If you are writing from a brief or real opinions**, use first-person. At least one "I" or "my" every 400 words. "I binged this in a weekend", "my favourite season", "I kept rewinding the pilot". Humans do this; LLMs avoid it by default.

**Hedge limit.** Max ONE hedged first-person construction per piece. "I think", "I'd argue", "my hunch is", "arguably", "in my view" are all hedges — pick at most one. Other first-person beats must be direct observations or lived details, not hedged opinions.

**Rewrite-mode inversion (the critical exception).** If you are REWRITING text that has ZERO first-person in the source, the rewrite has ZERO first-person. Do NOT invent lived experiences, viewer memories, or specific reactions. Fabrication is the single biggest harm mode. "I argued with Amanda by episode two" when the original contains no such memory is a meaning-level harm, not a style improvement. A rewrite with no first-person at all is a correct outcome when the source had none.

---

## Required: one deliberate imperfection per piece

Include at least one of:

- A fragment sentence (no verb). "Cold. Deliberate. That opening shot."
- A one-sentence paragraph used for emphasis.
- A parenthetical aside with mild self-awareness.
- A slightly informal word where a formal one would fit.

One. Not everywhere. Somewhere.

---

## Blockquote double-quote wrapper (specific fix)

If a blockquote is wrapped in straight double quotes at its start and end (e.g. `> "content in here."`), strip those wrapping quotes. This is a common drafting artefact, not intentional quotation. Keep the `>` marker and the content between the quotes; remove only the outermost `"` at the very start and very end. Preserve any INTERNAL quotes (reported speech, quoted titles, quoted words).

If the blockquote has an em-dash-led attribution ("— the general consensus" / "— critic name"), the em dash must go. Options: promote the attribution to a separate sentence beneath the blockquote, use a parenthetical, or rework the quote-plus-attribution into one paragraph. Do NOT silently drop the attribution.

---

## The three-pass workflow

### Sub-pass A — Mechanical scan (18 patterns, deterministic)

Scan the text. Every hit is a rewrite, not a warning.

| # | Pattern | Action |
|---|---|---|
| 1 | `/[—–‒―]/` | Replace with `,` `.` `:` or `()` per em dash replacement table |
| 2 | `/[\u2011]/` | Replace with ASCII `-` |
| 3 | `/[\u2018\u2019\u201C\u201D]/` | Replace with straight `'` or `"` |
| 4 | `/\u2026/` | Replace with `...` |
| 5 | `/;/` | Convert to `.` unless first and only in piece |
| 6 | `/\b(delve\|delves\|delving\|tapestry\|landscape\|testament\|navigate(s\|d)?\|resonate(s\|d)?\|nuanced\|multifaceted\|intricate\|underscore(s\|d)?\|unparalleled\|unprecedented\|groundbreaking\|meticulous(ly)?\|robust\|seamless\|holistic\|pivotal\|vibrant\|boasts\|nestled\|showcases?\|showcasing\|leverage(s\|d)?\|realm)\b/i` | Rewrite sentence |
| 7 | `/\bit['’]s not (just\|merely) .{1,40}(,\|;\| it['’]s )/i` | Rewrite without contrast frame |
| 8 | `/\bnot only .{1,40} but (also )?/i` | Rewrite |
| 9 | `/\bat its (core\|heart\|best\|worst)\b/i` | Rewrite |
| 10 | `/\b(stands as\|serves as\|marks a\|represents a)\b/i` | Rewrite to use "is" or be concrete |
| 11 | `/\b(it['’]s worth noting\|it['’]s important to\|it should be noted)\b/i` | Delete clause |
| 12 | `/\bnothing short of\b/i` | Delete or rewrite |
| 13 | `/\b(a masterclass in\|a love letter to\|a testament to)\b/i` | Rewrite |
| 14 | `/\b(in today['’]s (world\|landscape)\|in an era of\|in the ever-evolving)\b/i` | Rewrite opener |
| 15 | `/\bwhether you['’]re .{1,30} or .{1,30},/i` | Rewrite |
| 16 | `/\b(razor[- ]sharp\|pitch[- ]perfect\|career[- ](defining\|redefining)\|spot[- ]on\|dead[- ]on\|tour de force\|a masterstroke\|a triumph\|unspools?\|unfurls?\|crackles?\|crackling\|sings\|visceral\|searing\|haunting)\b/i` | Rewrite per banned praise compounds |
| 17 | `/\bone of the (best\|finest\|greatest\|most [\w-]+) (ever\|(ever )?(committed\|put\|seen) (to\|on)) (screen\|television\|tv\|film)\b/i` | Rewrite — cut "ever" framing |
| 18 | `/\bfinest of its kind\b/i` | Cut |

### Sub-pass A checklist

Fill honestly. If unsure, assume yes and rewrite — but subject to FIRST, DO NO HARM.

```
[ ] 0 em / en / figure dashes in piece
[ ] 0 non-breaking hyphens, 0 smart quotes, 0 ellipsis chars
[ ] <= 1 semicolon total
[ ] 0 banned vocabulary words
[ ] 0 banned praise compounds
[ ] 0 "not just X it's Y" constructions
[ ] 0 "at its core / heart / best / worst"
[ ] 0 "stands as / serves as / marks a / represents a"
[ ] 0 "it's worth noting / it's important to"
[ ] 0 "one of the X ever committed to screen/tv/film" framings
[ ] <= 1 tricolon (including link-laden ones)
[ ] <= 1 "whether X or Y"
[ ] <= 1 hedged first-person beat
[ ] <= 2 consecutive sentences of the same copula pattern
[ ] EVERY list item from the original preserved (zero drops)
[ ] In REWRITE mode: zero invented first-person beats
[ ] At least 1 fragment or one-sentence paragraph somewhere
```

### Sub-pass B — Structural rewrite (the important one)

Sub-pass A fixes tokens. Sub-pass B fixes rhythm, which is what actually moves detector scores.

For each paragraph:

1. **Sentence-length variation.** Count word counts. 3+ consecutive within 4 words of each other? Break or merge. Target: at least one sub-8-word sentence and one 25+-word sentence per 500 words.
2. **Parallel copula stacks.** Scan for 3+ consecutive `[Subject] is [Y]` or `[X]'s [Y] is [Z]`. Rewrite at least one — turn into a question, collapse two into one, add a concrete specific detail that breaks rhythm, or use a different verb. Max 2 consecutive.
3. **Paragraph shape.** Is this topic-sentence → 3 supports → summary? Break the template. Cut the summary. Start mid-thought. Let it end on a specific detail.
4. **Opening formula.** Does the section or paragraph open with "The [subject]...", "This [thing] is...", "At its core..."? Rewrite the opener to name something specific (a person, a scene, a choice).
5. **First person.** (Only if writing from scratch or the source had first-person to begin with.) If the source has zero first-person, DO NOT ADD ANY — this is the most common harm.
6. **One deliberate imperfection.** Fragment. Informalism. Aside. Somewhere in the piece. Not everywhere — just somewhere.

After Sub-pass B, re-run Sub-pass A — rewrites sometimes reintroduce banned vocab.

### Re-run Sub-pass A, then verify

One more pass through the 18 patterns and checklist. If the second run still finds hits, fix them and move on — do not loop forever.

Then explicitly grep the final text for zero hits of:

- Non-ASCII dashes: `—` `–` `‒` `―` `‑`
- Smart quotes: `'` `'` `"` `"` and ellipsis char `…`
- All banned vocab words
- All banned praise compounds
- `at its core`, `at its heart`, `stands as`, `serves as`, `marks a`, `represents a`
- `it's worth noting`, `it's important to`, `it should be noted`
- `nothing short of`, `a masterclass in`, `a love letter to`, `a testament to`
- `in today's world`, `in an era of`, `in the ever-evolving`
- `it's not just`, `it isn't just`, `it's not merely`, `not only .* but also`
- `ever committed/put/seen to/on screen|television|tv|film`
- `finest of its kind`

Cross-count lists: every list in the original present in the rewrite, same item count.

---

## Report format

Return the rewritten text AND a report with:

1. Before / after word count and character count
2. Number of em dashes removed
3. Banned-vocab words rewritten (per-word breakdown if more than a handful)
4. Banned-phrase constructions rewritten
5. Banned praise compounds rewritten (per-compound)
6. Sentences restructured for burstiness / for parallel copula stacks (broken out)
7. First-person additions (hedged vs direct). In rewrite mode this MUST be zero if source had none.
8. List restructures table — every list touched, original item count, rewrite item count (numbers must match)
9. Any section expanded and what with
10. Blockquote handling notes (wrapper quotes stripped, attributions handled)
11. Full after-text
12. Verification grep result
13. **Items KEPT despite AI rhythm** — every spot where you could have applied a rule but deliberately chose not to, and why. This is the most important section. Transparency is the protection against harm.

A long "kept" section with good reasoning is GOOD. A clean-looking report with hidden harms is BAD.

---

## Context — why this exists

Developed while generating TV reviews for TheAttReviews.com using Claude as an author-in-the-loop. Early iterations read exactly like the AI-generated content Google's classifiers are trained to flag.

Three rule-tuning rounds later:

1. First I banned the words. Minor improvement. Detectors still scored high because the rhythm was unchanged.
2. Then I added structural rules (burstiness, paragraph shape, parallel copula stacks). Bigger improvement — detector scores dropped, readers stopped clocking it.
3. Then I added FIRST, DO NO HARM after the agent started inventing reviewer memories ("I argued with Amanda by episode two" — I had never said that) and reallocating genre descriptors ("a modern gangster drama" got moved off the show I was reviewing onto comparators). That was the breakthrough. The de-AI pass has to be SUBORDINATE to meaning preservation. A clean-scoring rewrite with a fabricated memory is a failed rewrite, not a successful one.

The rules in this guide are what survived. Your domain will differ — adjust the banned-vocab list accordingly. The structural rules, the three-pass workflow, and FIRST, DO NO HARM are universal.
