# Meaning · Voice · Renderer

This repository documents a simple framework for separating **semantic ownership**
from **AI rendering** in product marketing.

It is not a software project. There is no code to run.

The purpose of this repository is to make explicit a division of responsibilities
that many teams already sense intuitively, but rarely formalize:

- product marketing owns meaning,
- downstream teams own voice and constrained personalization,
- AI acts as a renderer, not an author.

What follows is an essay that explains the model, why it matters, and how it can be
used in practice.

---

## Separating Meaning from Voice in Product Marketing

*How AI enables a clearer division of responsibilities, and where that division breaks down*

*Editor’s note: I’ve written a lot about personal AI experimentation. This piece widens the lens to a practical company use case. It looks at how product marketing teams can use AI to scale consistent content without losing semantic integrity or human credibility.*

---

## Why I’m widening the lens

If you’ve read my writing about AI before, most of it has been personal. I’ve spent time learning what it feels like to use AI as a writing partner. I’ve paid attention to where it helps, where it gets in the way, and what happens when the output sounds close to me but not quite right.

Lately, I’ve been running into a different class of questions. These aren’t about whether AI can help one person write. They’re about whether AI can help organizations communicate more consistently without flattening the message or drifting off position.

Personal use is where most of us start. The real leverage, and the real risk, shows up when AI is used across teams. Product marketing, brand, PR, sales, regional marketing, and agencies all touch the same core ideas. That’s where inconsistencies compound. That’s also where “good enough” copy quietly drifts off message.

This post is my attempt to connect those two worlds. The same issues I’ve been picky about in personal writing show up again at scale. Voice matters. Boundaries matter. Knowing what not to explain matters.

---

## What product marketing actually owns

At its core, product marketing is not responsible for writing copy. It is responsible for defining what a product means, who it is for, why it matters, what can and cannot be claimed, and how it should be positioned relative to alternatives.

Those are semantic decisions. They are not inherently prose.

The usual failure mode is familiar. Product marketing expresses these decisions as finished copy. Downstream teams then edit that copy to fit their channel, audience, and voice. Meaning and wording get coupled. Drift follows.

AI doesn’t fix that problem by itself. It makes the coupling more obvious.

---

## A three‑layer model

The model I’m proposing separates meaning, voice, and personalization into three explicit artifacts.

### 1) MESSAGING.md (meaning)

This is the canonical product marketing artifact. It captures positioning, value propositions, proof points, objections, and boundaries. It is not channel‑specific and not written for publication.

If something changes about the product’s meaning, it changes here.

### 2) VOICE.md (rendering constraints)

VOICE.md defines how the message should sound. That includes tone, diction, structure, and what to avoid.

There does not need to be one voice. Brand, PR, sales, and regional teams often need legitimately different voices.

VOICE.md changes how something is said. It does not change what is said.

### 3) PERSONALIZATION.md (optional local context)

PERSONALIZATION.md adds relevance without changing claims. It can include vertical context, regional framing, or situational emphasis.

It is additive, not generative. It must not introduce new promises or reposition the product.

---

## Who does what in this model

One reason this can feel abstract on first read is that “consumer” gets overloaded. Here, the consumer is not the end customer. It’s the internal role generating content: brand, PR, advertising, demand generation, sales enablement, regional marketing, and partners.

- MESSAGING.md is owned by product marketing.
- VOICE.md is owned by whoever owns the audience and channel.
- PERSONALIZATION.md is owned by whoever owns local context.

This model doesn’t remove governance. It makes governance visible. Meaning is reviewed upstream. Voice is constrained by explicit rules. Personalization is limited by design.

The cost is a bit more thinking up front. The payoff is far less rework downstream.

---

## How the pieces fit together

Stripped of prose and polish, the model looks like this:

```
MESSAGING.md  +  VOICE.md  +  (optional) PERSONALIZATION.md
        \______________  AI renderer  ______________/
                         |
                         v
     website copy • ad variants • email campaigns • sales sequences
     vertical versions • regional versions • partner‑ready assets
```

Everything else in this post is just different ways of rendering that same structure.

---

## Why Markdown

These artifacts are written in Markdown deliberately. AI systems infer importance from structure—headings, lists, emphasis, and hierarchy matter. Markdown is the lowest-friction way to encode that structure while staying human-readable.

The proposal is not that everyone becomes a prompt engineer. It’s that teams learn to express intent in a structured, readable format that both humans and AI can reason over.

---

## Where AI fits

AI is not the author in this model. It is the renderer. Given MESSAGING.md, VOICE.md, and optional PERSONALIZATION.md, AI assembles channel-specific outputs without inventing new meaning.

---

## A concrete example

To make this tangible, here is a hypothetical product: a compact folding umbrella that is waterproof and UV-protective, small enough for a purse or a small gear bag.

Below are sample inputs (MESSAGING.md, VOICE.md, PERSONALIZATION.md) and the kinds of outputs they can produce.

### Example MESSAGING.md (meaning)

```
# MESSAGING.md
## Product
**PocketShield Umbrella**
Compact folding umbrella with storm-ready waterproofing and UV protection.

## Positioning
A compact umbrella you actually carry—built for sudden rain and harsh sun.

## Target customers
- Urban commuters
- Frequent travelers
- Minimalists carrying small bags or gear slings

## Core value propositions
1. Carry it every day (compact and lightweight)
2. Trust it in heavy rain and gusts
3. Useful in sun as well as storms

## Boundaries
- Do not claim medical benefits
- Do not claim storm or hurricane immunity
```

### Example VOICE.md (global consumer brand)

```
# VOICE.md
## Brand voice
Calm, confident, and practical.

## Tone
- Clear and direct
- Global English
- Friendly, not chatty

## Avoid
- Buzzwords
- Exaggeration
- Slang or regional idioms
```

### Example PERSONALIZATION.md (sun + rain regions)

```
# PERSONALIZATION.md
## Regional context
Markets with frequent rain and strong sun.

## Local framing
- Sun one minute, rain the next
- Weather changes quickly

## Constraints
- Do not introduce new product claims
- Do not invent local statistics
```

## Example outputs rendered from the same inputs

### Website hero copy

```
PocketShield Umbrella
The compact umbrella you actually carry.
Built for sudden rain and harsh sun. Small enough to keep with you every day—without feeling flimsy when the weather turns.
One dependable umbrella for the weather you get, not the forecast you planned.
CTA: Shop PocketShield
```

### Paid social ad

```
Primary text: Sun one minute. Rain the next. PocketShield is the compact umbrella built for both.
Headline: One umbrella. Fewer tradeoffs.
CTA: Learn more
```

### Short email

```
Subject: The umbrella you’ll actually have with you
Body: Most umbrellas are either bulky or unreliable. PocketShield folds small enough to live in your bag, but it’s built for heavy rain and strong sun when the weather changes quickly. Take a look →
```

---

## Inspecting the actual inputs
I’m including the sample Markdown files used for this umbrella example as a downloadable bundle. The important thing is not the umbrella—it’s the structure.

Download: https://github.com/stevepao/meaning-voice-renderer/archive/refs/tags/V1.0.1.zip

---

## Try it yourself

Below is a single prompt you can paste into ChatGPT or Claude. The prompt itself is provided in raw Markdown, since the whole point is to make Markdown a shared input language.

```
# Prompt

## Role
You are an **AI content renderer** for product marketing assets. You do **not** invent meaning. You assemble approved inputs.

## Inputs
You will receive up to three Markdown inputs:

1. **MESSAGING.md** — authoritative meaning.
2. **VOICE.md** — rendering constraints.
3. **PERSONALIZATION.md** (optional) — constrained local context.

## Precedence
If inputs conflict: **MESSAGING.md > VOICE.md > PERSONALIZATION.md**

## Rules
- Treat **MESSAGING.md** as the source of truth.
- Apply **VOICE.md** as mandatory style constraints.
- Apply **PERSONALIZATION.md** only as constrained relevance.
- If a detail is missing, proceed without it rather than guessing.
- Avoid hype, overpromising, and medical/legal claims.

## Tasks
Generate three assets:

### A) Website hero section
- Headline
- Subhead
- 2 short paragraphs
- 1 CTA button label

### B) Paid social ad
- Primary text
- Headline
- Description (optional)
- CTA

### C) Short email
- Subject line
- Body under 120 words
- One clear CTA line

## Output format
- Label each asset clearly with Markdown headings.
- Keep claims consistent with **MESSAGING.md** boundaries.

---

## BEGIN MESSAGING.md
[paste MESSAGING.md here]
## END MESSAGING.md

---

## BEGIN VOICE.md
[paste VOICE.md here]
## END VOICE.md

---

## BEGIN PERSONALIZATION.md (optional)
[paste PERSONALIZATION.md here]
## END PERSONALIZATION.md
```
---

## Where this breaks down

This model works best for assets like website copy, advertising, email campaigns, and sales sequences—where consistency and adaptability must coexist.
It breaks down for founder stories, first-person thought leadership, and narrative essays. In those cases, meaning and voice co-emerge through lived discovery, and trying to separate them flattens the content.

---

## Conclusion

AI doesn’t change the need for judgment. It changes where that judgment belongs.
When PMM owns meaning and boundaries, downstream teams own voice and constrained personalization, and AI renders outputs, content scales without losing coherence. AI stops being magical and starts being useful.

If you want to try this without a reorg, pilot it with one launch. Have PMM publish a single MESSAGING.md, have brand publish one VOICE.md, have one field or vertical team publish one PERSONALIZATION.md, and then render three assets (web hero, paid social, one email). The goal of the pilot is not volume. It’s to prove that meaning stays stable while voice and context vary safely.

---

## Repository contents

- `README.md` — the framework and rationale
- `MESSAGING.md` — example of meaning as an explicit artifact
- `VOICE.md` — example of rendering constraints
- `PERSONALIZATION.md` — example of constrained local context
- `LICENSE` - Creative Commons Attribution 4.0 International License

---

## License

© Hillwork, LLC 
This work is licensed under a Creative Commons Attribution 4.0 International License.
