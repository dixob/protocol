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
| 02 | Japanese AI Interaction Guide | 🔧 In progress | Working in Japanese-language AI contexts; register and compression patterns |
| 03 | Multilingual Research Synthesis | 📋 Planned | Synthesizing sources across 2+ languages without translation-flattening |
| 04 | System Discovery & Implementation | 📋 Planned | Onboarding to an unfamiliar technical system and building in it |

---

## How to use a protocol

Each protocol is a Markdown file designed to be loaded into an AI session.

**In Claude (claude.ai):**
+robert comment: change this to be "any tool" not just claude.ai
1. Open a new conversation
2. Upload or paste the protocol file
3. State your task — the protocol's trigger conditions handle the rest

**In any other AI tool:** The protocols are written as instructions the model reads and follows. Paste the file contents as a system prompt or the first user message.

**What happens:** The AI reads the operational spec and executes it — asking the right questions, following the defined steps, applying quality standards, and producing output in the specified format. You don't need to manage the process.

---

## Protocol 01 — Study Guide Builder

**Trigger:** Upload the protocol + name a field you want to learn.

+ change description here - include something like "evidence based learning methodologies" or something.
**What it produces:** A personalized study guide — structured as a formatted document or interactive HTML app — with concept maps, flashcards, gap bridges, visual keys, and verbal scripts. Calibrated to your goal (exam, interview, project, curiosity) and your current knowledge level.

**Three depth levels:**
- **Quick Start (A):** Concept map + 15 flashcards + key facts drill. ~15 min.
- **Solid Foundation (B):** A + analogies, gap bridges, visual diagrams, verbal scripts. ~30 min.
- **Full Guide (C):** B + misconception map, "never say this" list, expert debates. ~45–60 min.

→ [Full specification](protocols/01-study-guide-builder.md)

---

## Why protocols, not prompts

+would it make sense to talk about the non-deterministic nature of LLMs here? prompts = randomness, protocols = reproducibility. check for validity
Prompts degrade. After a few sessions, you're re-specifying the same constraints — the same format requirements, the same quality gates, the same instructions not to over-explain the methodology. Protocols encode those decisions once and apply them consistently.

The protocols in this library were developed through direct AI consulting work, tested against real output quality, and refined until the failure modes were explicitly documented and handled. They're not theory — they're specs that have been run.

---

## Project status

This library is actively being built. Current focus: Protocol 01 (available) and Protocol 02 (in progress, covering Japanese-language AI interaction patterns — a less-documented area with distinct behavior from English-language prompting).

---

*Built as part of a portfolio of deployable AI tools. See also: [GitHub profile](https://github.com).*
