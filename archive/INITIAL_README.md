> This is a small exploratory project, not a production classifier or authorship detector.
# Rhetorical Mirror

A small experiment for inspecting the rhetorical scaffolding inside posts, emails, and AI-assisted social writing.

This repo is not a detector for whether a human or AI "really wrote" a post.

It is a mirror.

The goal is to surface the persuasion frameworks, narrative tropes, rhetorical devices, and platform tactics that often appear in social content — especially when that content is generated or heavily shaped by large language models.

The idea is simple:

When you ask an AI to write a "good LinkedIn post," the result often feels familiar for a reason. It tends to reproduce old copywriting structures, social-platform formatting habits, and engagement tactics that already perform well.

So instead of arguing about whether that is good or bad, this repo tries to make those patterns visible.

It is not a scientific benchmark or a competitive taxonomy project.

It is a practical mirror you can run against your own drafts.

## What is in this repo

This repo currently contains two core artifacts:

- [`prompts/mirror-prompt.md`](../prompts/mirror-prompt.md): a copy-paste prompt you can run in any capable LLM to analyze a draft
- [`taxonomy/taxonomy.json`](../taxonomy/taxonomy.json): a structured taxonomy for classifying rhetorical patterns in social content

Together, they support a few practical use cases:

1. **Manual inspection**  
   Paste a draft into the prompt and get a rhetorical self-audit.

2. **Draft cleanup**  
   Ask a model to rewrite a draft so it stays grammatical, factual, and low on sales or marketing language.

3. **Lightweight structured evaluation**  
   Use the taxonomy in an LLM workflow, agent pipeline, CLI, or content review step.

## Why this exists

This started as a simple observation:

A lot of what people call "AI LinkedIn voice" does not feel new.

It feels like older sales and copywriting logic showing up in a new interface.

The patterns are recognizable:
- **PAS** (Problem–Agitate–Solve)
- **AIDA** (Attention–Interest–Desire–Action)
- **HSO** (Hook–Story–Offer)

And the packaging is recognizable too:
- one-line paragraphs
- curiosity gaps
- generic engagement bait
- disguised calls to action

The taxonomy in this repo groups common patterns into several high-level layers:
- persuasion frameworks
- narrative tropes
- persuasion techniques
- rhetorical devices
- logical fallacies
- cognitive biases
- platform and pressure tactics

It stays intentionally high-level rather than trying to become a giant persuasion ontology.

This is not an anti-AI project.

It is also not a moral purity test.

The point is to inspect the rhetorical machinery in a piece of writing, whether it got there intentionally, unconsciously, or through AI assistance.

## The "mirror, not judge" principle

The core prompt is intentionally framed as a **mirror, not a judge**.

That matters.

Using rhetorical structure is not automatically manipulative.
Using a framework intentionally can be completely legitimate.
The problem is not that these patterns exist.

The problem is not noticing when they are doing the heavy lifting for you.

That principle is built directly into the prompt: it is descriptive rather than prescriptive, and aims to show the author what is happening without pretending every framework is inherently bad.

## What the prompt does

The prompt analyzes a piece of content across several high-level layers:

### 1. Persuasion frameworks
Examples:
- PAS
- AIDA
- HSO

These are the large structural patterns that shape the post from opening to close.

### 2. Narrative tropes
Examples:
- Performative vulnerability
- Contrarian humblebrag
- Parasocial mentor
- Storyselling

These are the character positions or personas the author is implicitly performing.

### 3. Persuasion techniques
Examples:
- Loaded language
- Appeal to authority
- Appeal to fear
- Social proof

These are common persuasive moves that make a claim feel urgent, credible, emotional, or socially validated.

### 4. Rhetorical devices
Examples:
- Curiosity gap
- Specificity theater
- Moral compression
- Safe contrarianism

These are the smaller linguistic and structural tricks that make persuasion feel natural or invisible.

### 5. Logical fallacies
Examples:
- False dilemma
- Hasty generalization
- Causal oversimplification
- Cherry-picking

These are reasoning shortcuts that make an argument feel cleaner or stronger than it really is.

### 6. Cognitive biases
Examples:
- Confirmation bias
- Loss aversion
- Halo effect
- Anchoring

These are judgment shortcuts a piece of writing may lean on or activate in the reader.

### 7. Platform and pressure tactics
Examples:
- Broetry
- Engagement farming
- Disguised CTA
- Fake scarcity
- Artificial urgency

These are packaging choices designed for feed algorithms and platform behavior, not necessarily for clarity.

## Output format

The prompt asks the model to return five parts:

- **What your draft is doing**
- **Detected patterns**
- **Substance extraction**
- **Your rhetorical fingerprint**
- **One thing to consider**

The most important section is probably **Substance extraction**.

That is the part where the rhetorical scaffolding gets stripped away and the underlying claims are restated plainly.

If that section comes back thin, that usually tells you something useful.

## Quick start

### Option 1: use the prompt directly

Open [`prompts/mirror-prompt.md`](../prompts/mirror-prompt.md), copy it into your model of choice, and replace:

`[PASTE YOUR DRAFT HERE]`

with the text you want to inspect.

### Option 2: use the taxonomy in code

Open [`taxonomy/taxonomy.json`](../taxonomy/taxonomy.json) and feed it to your model alongside the target text.

The taxonomy was written to support structured tagging of detected patterns, confidence levels, and extraction of underlying substance. Its intended usage is explicitly described in the file metadata.

### Option 3: use it as a rewrite guardrail

You can also ask the model to use the taxonomy while rewriting a draft.

A practical instruction looks like this:

- check grammar, but do not over-polish
- remove marketing and sales jargon
- keep the wording close to how I normally write emails
- answer plainly: what this is about, what problem it solves, why it matters, and how it works
- keep rhetorical density low

A natural next step would be:
- define a JSON schema
- force the model to return structured output
- score drafts by rhetorical density vs. substantive density
- use the result to simplify a draft before sending or posting

## Example use cases

A few possible uses:

- self-auditing your own draft before posting
- comparing multiple AI-generated versions of the same post
- inspecting whether an agent is drifting into generic marketing language
- building a CLI or API that classifies rhetorical patterns
- studying how AI-assisted writing tends to inherit old persuasion frameworks

## What this repo is **not**

This repo is **not**:

- a reliable AI authorship detector
- a scientific benchmark or a comprehensive persuasion ontology
- a claim that rhetorical structure is inherently dishonest
- a claim that every short line or strong hook is manipulation
- a finished product

It is just a small, open-ended tool for inspecting a pattern that seems increasingly common.

## Self-assessment

This repo itself should probably be read with the same mirror in mind.

Even the explanation of this project can easily slip into the patterns it is describing:
- a mildly contrarian framing
- a neat explanatory arc
- a satisfying reduction of a messy cultural pattern into a compact taxonomy

That does not invalidate the project.

If anything, it is a reminder that rhetorical structure is everywhere — including in attempts to explain rhetorical structure.

To see this in practice, here is [the mirror's evaluation of this README](../examples/initial-readme-evaluation-example.json).

## Repo structure

```text
rhetorical-mirror/
├─ LICENSE
├─ NOTICE
├─ README.md
├─ prompts/
│  └─ mirror-prompt.md
├─ taxonomy/
│  └─ taxonomy.json
├─ examples/
│  └─ initial-readme-evaluation-example.json
```

## License

Copyright 2026 Nenad Micic.

This project is licensed under the Apache License 2.0. See [`LICENSE`](../LICENSE) for the full license text and [`NOTICE`](../NOTICE) for the attribution notice.
