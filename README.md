# Builder Coliving Finder

An AI research prompt that finds **builder coliving** programs worldwide: villas,
houses, and communities where founders, engineers, and remote workers live
together and build their own projects.

Drop the prompt into any research-capable AI tool with web search and it returns
a ranked, sourced shortlist filtered to your budget, your visa situation, and
whether the program lets you keep your own remote work going.

## The problem

The "founder house" scene is real and growing, but it is scattered and noisy.
Some are intense equity residencies that forbid outside work. Some are relaxed
coliving villas you can join next week. Listings go stale fast, pricing is often
hidden, and almost nobody tells you whether your passport can actually get you a
long stay. Searching this by hand is slow and the results are shallow.

This prompt does the structured work: it defines the concept tightly, separates
the two program types, filters against the constraints that actually matter, and
forces the model to verify and cite rather than guess.

## What it searches for

Residential communities where people live and build together, in two categories
the prompt labels separately:

- **(A) Structured residencies and cohorts** with fixed dates, an application,
  and sometimes demo days or investment.
- **(B) Open-enrollment coliving** you can join anytime while keeping your own
  work and income.

It covers founder houses, hacker houses, AI builder villas, startup residencies
with housing, and coliving plus coworking communities for remote workers. It
deliberately excludes plain hotels, hostels, and pure coworking with no living
component.

## Key filters

Every result is marked against the things that make or break a real move:

- Does it **allow outside work and remote income**? Many residencies do not.
- **Monthly all-in cost**, with sharing factored in.
- **Visa reality** for your specific passport, plus the local digital-nomad visa.
- **Internet quality** and **timezone** versus your clients.

## How to use it

1. Open one of the prompt files in `/prompts`.
2. Edit the `MY PROFILE` block to match your situation.
3. Paste it into an AI tool that can browse the web. Web search matters here,
   because this scene changes month to month and the model's memory will be stale.
4. Read the comparison table, then dig into the ranked shortlist.

## Versions

| File | Use it when |
|------|-------------|
| [`prompts/builder-coliving-finder.md`](prompts/builder-coliving-finder.md) | The full, personalized prompt. Start here. |
| [`prompts/deep-research-version.md`](prompts/deep-research-version.md) | You're running a long, multi-step deep-research agent. |
| [`prompts/generic-version.md`](prompts/generic-version.md) | You want a clean, shareable version with no personal details. |

## Example output shape

The prompt asks the model to return:

1. A comparison table of 12 to 20 verified matches (name, type, location, monthly
   cost, allows outside work, visa ease, apply link).
2. A ranked top 5 with a short rationale for each.
3. Full source citations, and an honest "could not verify" list rather than
   invented entries.

## Why I built it

I build AI and e-commerce tools and work remotely, so I wanted a repeatable way
to scout places to live and build alongside other people doing the same. Rather
than re-googling it every few months, I turned the research into a prompt I can
re-run anytime and hand to anyone.

## License

[MIT](LICENSE) © 2026 Riza Balci
