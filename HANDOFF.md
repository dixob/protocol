# Session Handoff — AI Protocol Library

**Project:** ai-protocol-library (Portfolio Project 6)
**Last updated:** 2026-03-10
**Status:** Protocol 01 complete. Protocol 02 is next.

---

## What this project is

An "AI Protocol Library" — a GitHub repository of deployable operational specifications for AI-assisted knowledge work. The key distinction: **these are protocols, not prompts**. A protocol is a structured document you load into an AI session that defines trigger conditions, step-by-step behavior, output format standards, quality gates, and failure modes. It operates across an entire class of tasks, not just one request.

This is Portfolio Project 6, positioned as a differentiator: the library demonstrates systems thinking about AI (spec-writing, not just prompt-writing), and Protocol 02 in particular draws on direct Japan-market consulting experience — a hard-to-replicate professional signal.

---

## Completed work

### PRD
`/showcase/AI_Protocol_Library_PRD.docx` — 28KB, 459 paragraphs, validated.
Full product requirements document covering: vision & positioning, target audience, success criteria, 4-protocol content plan, repository structure, protocol template standard, build order, phase 2 scope, differentiation analysis, open questions. Written for a recruiter + technical audience. The 90-second test is the primary success criterion for the repo landing page.

### Repo files (ready to push to GitHub)
```
ai-protocol-library/
├── README.md                              ← Landing page, passes 90-sec test
└── protocols/
    └── 01-study-guide-builder.md          ← Full spec, public-ready
```

**README.md** — Opens with the pitch, explains protocol vs. prompt distinction via table, shows all 4 protocols with status indicators, explains how to use, and describes Protocol 01. Clean. No proprietary refs.

**01-study-guide-builder.md** — 591 lines, dual-audience structure. First section (5 lines) is for the user: how to activate. Everything below is the operational spec for the AI. All 8 sections, 10 blocks, ASCII diagram templates, failure mode table, quick reference card. Adapted from `study_guide_protocol (1).docx` with no proprietary references.

---

## Source files (reference only, not to push)
- `/mnt/uploads/study_guide_protocol (1).docx` — Original Study Guide Builder (the source for Protocol 01). Already adapted.
- `/mnt/showcase/GitHub_Projects_Dev_Plan.md` — Master portfolio dev plan. Project 6 is current focus.
- `/mnt/showcase/AI_Protocol_Library_PRD.docx` — Full PRD with build order and open questions.

---

## Build order (from PRD Section 7)

| Step | Task | Est. time | Status |
|---|---|---|---|
| 1 | Create `ai-protocol-library` GitHub repo | 15 min | ⬜ Not started |
| 2 | Push README + Protocol 01 | 15 min | ⬜ Not started (files are ready) |
| 3 | Configure GitHub Pages | 15 min | ⬜ Not started |
| 4 | **Write Protocol 02** (Japanese AI Interaction Guide) | 4–6 hrs | ⬜ Not started — **NEXT** |
| 5 | Write Protocol 03 (Multilingual Research Synthesis) | 3–4 hrs | ⬜ Not started |
| 6 | Write Protocol 04 (System Discovery & Implementation) | 3–4 hrs | ⬜ Not started |

---

## Protocol 02 — what needs to be written

This is the most original and differentiating protocol in the library. It covers how to interact with AI systems in Japanese — specifically the patterns used by professional Japanese AI practitioners that differ from the "polite verbose" approach many tools default to.

### Core sections to write:

**Register Selection Framework** — When to use which register:
- 丁寧語 (polite/desu-masu) — general use, first contact
- 普通体 (plain form) — iterative work, efficiency-focused
- 命令形 (imperative/command form) — task execution, the "expert mode"

The protocol needs to explain *why* each register produces different AI behavior, not just when to use it.

**Compression Pattern Catalog** — This is the key observation from GenerativeX. Expert Japanese AI users write terse, command-like instructions. The example that surfaced in prior sessions:
> "展開して。NPMとかYarnでできそう。"
> (Expand it. Looks like it could work with NPM or Yarn.)

vs. what a non-native or beginner Japanese AI user writes: verbose, polite, heavily hedged. The protocol needs 8+ documented compression patterns with examples of both forms.

**Evaluation Rubric** — How to assess whether a Japanese-language AI output is actually idiomatic vs. just grammatically correct. This is the failure mode most practitioners miss: the AI sounds grammatically fine but produces oddly formal or robotic output because the input was over-specified.

**Translation Context Module** — For practitioners working in bilingual contexts: when to prompt in Japanese vs. English for different task types, and why the language of the instruction affects the language of the reasoning, not just the output.

### Research backing (to cite in the protocol):
- Edward T. Hall, *Beyond Culture* (1976) — high-context/low-context communication framework. Japanese is the canonical example.
- 省略 (grammatical ellipsis) and 文脈依存性 (context dependency) are well-documented Japanese linguistic features. Shibatani's *The Languages of Japan* covers ellipsis substantively.
- Frame the Japan observations explicitly as practitioner-sourced from direct AI consulting work. This framing is honest and more credible to a technical reader than a survey.

### On expanding beyond anecdote:
There are no publicly available LLM datasets that are useful for this specific claim — WildChat, LMSYS, ShareGPT exist but are English-dominant and have no native speaker/cultural metadata. The right approach is:
1. Cite existing linguistic literature (Hall, Shibatani) for the underlying phenomenon
2. Source naturalistic examples from Qiita, Zenn, and Twitter/X (`#プロンプト`, `#プロンプトエンジニアリング`)
3. Frame the protocol as practitioner research explicitly — this is a strength, not a gap

---

## Open questions (from PRD Section 10)

| Question | Status |
|---|---|
| GitHub username — needs to appear in repo URL and README footer | ⬜ Resolve before pushing |
| GenerativeX attribution — how explicit to be in Protocol 02? Name the company, say "Japan-market AI consulting", or just "direct practitioner observation"? | ⬜ Decision needed |
| Japanese examples in Protocol 02 — inline in the .md file, or separate examples/ directory? | ⬜ Decision needed |
| Real vs. fabricated example outputs in Protocol 02 — use actual AI outputs you've generated, or constructed examples? | ⬜ Decision needed |

---

## Files to push to GitHub (when ready)

```
README.md
protocols/01-study-guide-builder.md
```

These are clean and public-ready. No proprietary references. Verified.

---

## To resume in a new session

Say: **"I'm continuing the AI Protocol Library project. Read the HANDOFF.md in the ai-protocol-library folder and let's write Protocol 02."**

The PRD is at `/mnt/showcase/AI_Protocol_Library_PRD.docx` if deeper context is needed.
