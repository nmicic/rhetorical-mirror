# Rhetorical Mirror

A small prompt-and-taxonomy repo for reducing AI-shaped voice drift in drafts.

I use AI a lot, but I do not want AI to make me sound like a person I am not.

This repo is a small guardrail for keeping posts and emails closer to my actual voice: plain, factual, and low on unnecessary self-promotion.

It is mainly a self-editing aid for my own drafts, though others may find it useful.

This repo is not an authorship detector, a scientific benchmark, a truth classifier, or a tool for judging other people.

It is a mirror.

## What It Is For

Use it when you want a model to:

- check grammar
- keep your voice reasonably intact
- remove marketing or sales language
- answer plainly: what this is about, what problem it is trying to solve, why it matters, and how it works
- start high-level and add more detail later
- keep rhetorical density low

## Why This Exists

AI-assisted drafts often become smoother, louder, and more performative than I would naturally write.

Large models pick up familiar patterns:

- persuasion frameworks
- authority borrowing
- emotional loading
- tidy oversimplifications
- feed or inbox pressure tactics

Sometimes that is intentional. Sometimes it is not.

I am less interested in sounding polished than in sounding like myself.

The point here is to make those patterns visible and, if needed, rewrite the draft in a plainer way.

## Important Limit

A high rhetorical density score does not mean a draft is false.

A low rhetorical density score does not mean a draft is true.

The score is about packaging, not factual correctness.

One reason for keeping this repo small and practical is to avoid turning it into a blunt classification tool that people use at scale to discard anything that sounds too polished or too shaped.

This repo is about style drift and rhetorical packaging, not about deciding whether a person is honest.

## What Is In The Repo

- [`prompts/mirror-prompt.md`](./prompts/mirror-prompt.md): the main prompt for analysis and low-rhetoric rewriting
- [`taxonomy/taxonomy.json`](./taxonomy/taxonomy.json): a high-level taxonomy of rhetorical patterns
- [`examples/readme-evaluation-example.json`](./examples/readme-evaluation-example.json): the current README's self-evaluation
- [`examples/initial-readme-evaluation-example.json`](./examples/initial-readme-evaluation-example.json): the earlier README's self-evaluation
- [`archive/INITIAL_README.md`](./archive/INITIAL_README.md): the earlier README snapshot

## Practical Prompt

Use this with the taxonomy and your draft:

```text
Here is my post or email.

Please check the grammar and rewrite it so it does not use marketing or sales language.

It should answer, plainly:
- what this is about
- what problem it is trying to solve
- why it matters
- how it works

Keep it factual.
Do not over-polish it.
Keep it human and reasonably close to my normal email style.
Start high-level and add more detail later.
Run it against taxonomy.json and aim for a low rhetorical density score.
```

If possible, give the model the full [`taxonomy/taxonomy.json`](./taxonomy/taxonomy.json) file as context, not just the shortened summary inside the prompt.

## How The Taxonomy Is Organized

The taxonomy is intentionally high-level.

It groups common patterns into these buckets:

- persuasion frameworks
- narrative tropes
- persuasion techniques
- rhetorical devices
- logical fallacies
- cognitive biases
- platform and pressure tactics

It is not trying to be exhaustive.

It includes both social-post patterns and a few email-specific tactics.

## Typical Workflow

1. Open [`prompts/mirror-prompt.md`](./prompts/mirror-prompt.md).
2. Give the model the full [`taxonomy/taxonomy.json`](./taxonomy/taxonomy.json) file as context.
3. Paste your draft.
4. Ask for a rewrite toward a low rhetorical density score.
5. Review the detected patterns, the substance extraction, the substance check, and the rewrite.
6. Keep or reject changes manually.

## README Examples

- Current README evaluation: [`examples/readme-evaluation-example.json`](./examples/readme-evaluation-example.json)
- Initial README snapshot: [`archive/INITIAL_README.md`](./archive/INITIAL_README.md)
- Initial README evaluation: [`examples/initial-readme-evaluation-example.json`](./examples/initial-readme-evaluation-example.json)

## Repo Structure

```text
rhetorical-mirror/
├─ LICENSE
├─ NOTICE
├─ README.md
├─ archive/
│  ├─ INITIAL_README.md
├─ prompts/
│  └─ mirror-prompt.md
├─ taxonomy/
│  └─ taxonomy.json
└─ examples/
   ├─ initial-readme-evaluation-example.json
   └─ readme-evaluation-example.json
```

## License

Copyright 2026 Nenad Micic.

This project is licensed under the Apache License 2.0. See [`LICENSE`](./LICENSE) for the full license text and [`NOTICE`](./NOTICE) for the attribution notice.
