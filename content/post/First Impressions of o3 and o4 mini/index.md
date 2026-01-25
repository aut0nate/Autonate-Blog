---
title: "First Impressions of o3 and o4-mini"
date: 2025-04-28
tags: [ai, llm, chatgpt]
---

I’ve been keeping an eye on OpenAI’s reasoning models since **[o1](https://openai.com/index/introducing-openai-o1-preview/)**, which launched on **12 September 2024** as the first reasoning model released by OpenAI. It signalled a shift towards models that can spend more time thinking through complex problems, and providing thorough analysis, rather than optimising purely for speed and conversational flow.

With [**o3** and **o4-mini**](https://openai.com/index/introducing-o3-and-o4-mini/), OpenAI is pushing that direction further. These are positioned less as general chat upgrades and more as models designed for deliberate, structured reasoning and tool-aware problem solving.

That said, if I’m honest, I haven’t yet had many everyday workflows that truly demand “deep thinking” models. Most of what I do day to day is handled well by faster general models. The reason I’m writing this now is that I want to explore **o3** and **o4-mini** in more detail and see where, if anywhere, these more powerful reasoning models fit naturally into my workflow.

## What are “reasoning models”?

In plain terms, reasoning models are designed to **think longer before answering**. The goal is not just to generate a plausible response, but to work through problems more carefully and reliably.

In practice, this tends to show up as:

* Better performance on multi-step tasks where the answer is not obvious
* Stronger constraint-following when the prompt has lots of requirements
* More consistent step-by-step problem solving
* Better decisions about when to use tools or ask clarifying questions

If a standard chat model is ideal for rapid answers, drafting, and everyday Q&A, a reasoning model is the one you reach for when you want something closer to:

* "Provide deep analysis on..."
* “Think this through in depth"
* “Work methodically and verify assumptions”

## What’s new with o3 and o4-mini?

OpenAI’s positioning is fairly clear:

* **o3** is the most capable option, aimed at harder reasoning problems.
* **o4-mini** is the more efficient reasoning model, designed for high-volume use while still benefiting from structured thinking.

The part I’m most interested in is not benchmark talk, but how these models behave in real tasks, especially when there are trade-offs, constraints, and incomplete information.

## Where I think I might use them

Even though I don’t yet have many proven use cases, here are the areas I want to test deliberately.

### Linux troubleshooting that needs a method, not a guess

When a service is failing, logs are messy, and there are multiple plausible causes, the most useful thing is a structured triage plan. I want to see whether o3 and o4-mini are better at:

* Asking the right clarifying questions in the right order
* Proposing a sensible diagnostic path rather than jumping to a fix
* Adapting as new evidence arrives

### Docker and Compose work with constraints

Docker tasks often look simple until you add real constraints, such as least privilege, networking boundaries, healthchecks, persistent storage, and clear upgrade paths.

I want to see whether a reasoning model is better at:

* Spotting subtle issues in Compose files
* Explaining trade-offs rather than stating preferences
* Helping produce repeatable baseline patterns I can reuse

### API workflows that involve friction

APIs are rarely clean in practice. Authentication edge cases, pagination, rate limits, and awkward response shapes quickly turn into multi-step problem solving.

I plan to test whether these models can help me:

* Build more reliable workflows
* Think through response handling step by step
* Debug failures systematically without trial-and-error spirals

## o3 vs o4-mini

Right now, I’m thinking about it like this:

* **o3** for genuinely complex problems which require thorough analysis
* **o4-mini** for throughput, when I want structured reasoning but need speed and repetition

## Final thoughts

Reasoning models feel like a shift from “chat that answers” to “an assistant that can plan and work methodically”. o1 was the first sign of that direction, and o3 and o4-mini look like the next step.

For now, I’m not claiming these models are essential to my current workflow. I simply haven’t had many situations where I truly need deep thinking. But I’m going to explore o3 and o4-mini in more detail, and see where their strengths can genuinely add value.
