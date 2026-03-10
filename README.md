# AI Protocol Library

**Operational specifications for AI-assisted knowledge work.**

This is not a prompt list. These are deployable specs — structured documents you load into an AI session to enforce consistent methodology across repeatable work tasks. Each protocol defines trigger conditions, step-by-step behavior, output format standards, quality gates, and failure modes.

---

## What's the difference between a protocol and a prompt?

A prompt tells an AI what to do once. A protocol tells an AI how to operate across an entire class of tasks — handling edge cases, ambiguity, format variance, and quality standards without you having to re-specify them each time.

| | Prompt | Protocol |
|---|---|---|
| **Scope** | One request | One class of tasks |
| **When it applies** | You write it | Defined trigger conditions |
| **Quality control** | Your judgment each time | Built-in standards and failure modes |
| **Reusable** | Copy-paste | Upload once, invoke anytime |
| **Adapts to context** | You adapt it | Adaptation rules are specified |

---

## Protocols

| # | Name | Status | Best for |
|---|---|---|---|
| 01 | [Study Guide Builder](protocols/01-study-guide-builder.md) | ✅ Available | Learning any field — exam prep, interviews, projects, self-study |
| 02 | [Japanese AI Interaction Guide](protocols/02-japanese-ai-interaction-guide.md) | ✅ Available | Working in Japanese-language AI contexts; register and compression patterns |
| 03 | Multilingual Research Synthesis | 📋 Planned | Synthesizing sources across 2+ languages without translation-flattening |
| 04 | System Discovery & Implementation | 📋 Planned | Onboarding to an unfamiliar technical system and building in it |

---

## How to use a protocol

Each protocol is a Markdown file designed to be loaded into an AI session.

**In any AI tool (Claude, ChatGPT, Gemini, etc.):**
1. Open a new conversation
2. Upload or paste the protocol file as your first message
3. State your task — the protocol's trigger conditions handle the rest

**What happens:** The AI reads the operational spec and executes it — asking the right questions, following the defined steps, applying quality standards, and producing output in the specified format. You don't need to manage the process.

---

## Protocol 01 — Study Guide Builder

**Trigger:** Upload the protocol + name a field you want to learn.

**What it produces:** A personalized study guide — structured as a formatted document or interactive HTML app — built on learning science principles (concept maps, active recall, spaced repetition) rather than generic summarization. Calibrated to your goal (exam, interview, project, curiosity) and your current knowledge level.

**Three depth levels:**
- **Quick Start (A):** Concept map + 15 flashcards + key facts drill. ~15 min.
- **Solid Foundation (B):** A + analogies, gap bridges, visual diagrams, verbal scripts. ~30 min.
- **Full Guide (C):** B + misconception map, "never say this" list, expert debates. ~45–60 min.

→ [Full specification](protocols/01-study-guide-builder.md)

---

## Protocol 02 — Japanese AI Interaction Guide

**Trigger:** Upload the protocol + start your session in the target language.

**What it produces:** Expert-register Japanese AI output — natural to a native reader, not translated or rendered from English. Covers register selection, eight compression patterns observed in professional Japanese AI usage, bilingual switching logic, translation and localization guidance, and a four-dimension evaluation rubric.

**The core insight:** In Japan's professional AI user community, the highest-competency users do not write polite, formal prompts. They write terse, compressed, command-line-style instructions that assume high context. This protocol documents those patterns — observed across field delivery engineers at a Japan-market AI consulting firm — and makes them reproducible.

**Three register levels:**
- **丁寧語 (polite):** First contact, formal contexts, business-facing output
- **普通体 (plain form):** Iterative work, internal documents, peer register
- **命令形 (command):** Task execution, code, expert mode — the pattern this protocol is built around

→ [Full specification](protocols/02-japanese-ai-interaction-guide.md)

---

## Protocols vs. native skills (Cowork, Claude Code, etc.)

Some AI platforms — like Anthropic's Cowork or Claude Code — support *native skills*: installed capabilities that live on disk, auto-trigger based on context, and can run code, call tools, and chain multi-step workflows. These are more powerful in their native environment. But they're also locked to it.

Protocols are the portable alternative.

| | Protocol | Native Skill |
|---|---|---|
| **Works in** | Any AI tool (Claude, ChatGPT, Gemini, etc.) | Only the platform it's installed on |
| **Triggered by** | You — load it when you need it | The system — auto-invoked by the runtime |
| **Context cost** | Full text loaded per session | Read once at invocation, minimal ongoing overhead |
| **Can run code/tools** | No — instructions only | Yes — full tooling access |
| **Portable** | Yes — one file, works anywhere | No — tied to runtime and file system |
| **Inspectable** | Yes — plain Markdown, human-readable | Depends on platform |

**When to use a protocol over a skill:** When you need the behavior to travel with you across tools, when you want the spec to be readable and shareable, or when you're working in an environment where you can't install anything. Protocols sacrifice automation for portability — that's a deliberate tradeoff, not a limitation.

---

## Why protocols, not prompts

Prompts are session-bound. The constraints live in your head, so output quality varies every time — different session, different result, different standard. Protocols make quality reproducible: the spec travels with the task, not the person running it.

Prompts degrade. After a few sessions, you're re-specifying the same constraints — the same format requirements, the same quality gates, the same instructions not to over-explain the methodology. Protocols encode those decisions once and apply them consistently.

The protocols in this library were developed through direct AI consulting work, tested against real output quality, and refined until the failure modes were explicitly documented and handled. They're not theory — they're specs that have been run.

---

## Project status

This library is actively being built. Current focus: Protocol 01 (available) and Protocol 02 (in progress, covering Japanese-language AI interaction patterns — a less-documented area with distinct behavior from English-language prompting).

---

*Built as part of a portfolio of deployable AI tools. See also: [GitHub profile](https://github.com).*
