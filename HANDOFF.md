# Session Handoff — AI Protocol Library

**Project:** ai-protocol-library (Portfolio Project 6)
**Last updated:** 2026-03-10
**Status:** Phase 1 — 2 of 4 protocols complete. Protocol 02 written and published. Next: Protocol 03.

---

## What this project is

An "AI Protocol Library" — a GitHub repository of deployable operational specifications for AI-assisted knowledge work. The key distinction: **these are protocols, not prompts**. A protocol is a structured document you load into an AI session that defines trigger conditions, step-by-step behavior, output format standards, quality gates, and failure modes. It operates across an entire class of tasks, not just one request.

This is Portfolio Project 6, positioned as a differentiator: the library demonstrates systems thinking about AI (spec-writing, not just prompt-writing), and Protocol 02 in particular draws on direct Japan-market consulting experience — a hard-to-replicate professional signal.

---

## Completed work

### PRD
`/showcase/AI_Protocol_Library_PRD.docx` — 28KB, 459 paragraphs, validated.
Full product requirements document covering: vision & positioning, target audience, success criteria, 4-protocol content plan, repository structure, protocol template standard, build order, phase 2 scope, differentiation analysis, open questions.

### Repo files (ready to push to GitHub)
```
ai-protocol-library/
├── README.md                                          ← Landing page, passes 90-sec test; updated with Protocol 02 section
└── protocols/
    ├── 01-study-guide-builder.md                     ← Full spec, public-ready (591 lines)
    └── 02-japanese-ai-interaction-guide.md           ← Full spec, public-ready
```

**README.md** — Protocol 02 status updated to ✅. Protocol 02 summary section added (same format as Protocol 01). All links correct.

**01-study-guide-builder.md** — Unchanged. Dual-audience structure, 8 sections, 10 blocks, ASCII diagram templates, failure modes, quick reference card.

**02-japanese-ai-interaction-guide.md** — Full spec. Dual-audience structure. 10 sections:
- Section 1: Operational Protocol (trigger conditions, prerequisites)
- Section 2: The Core Insight (expert/novice divergence, why it produces different output, linguistic grounding — Hall + Shibatani)
- Section 3: Register Selection Framework (3 registers + selection table)
- Section 4: Compression Pattern Catalog (8 patterns with expert/novice examples)
- Section 5: Bilingual Switching Logic (4 rules including Robert's rebuild pattern)
- Section 6: Activation Patterns (A: self-exemplifying declaration, B: English meta-instruction, C: implicit)
- Section 7: Translation Context Module (prompt language selection, translation vs localization, game localization failure modes from Amazon Games QA experience, translation brief template)
- Section 8: Evaluation Rubric (4 dimensions: register accuracy, compression integrity, cultural register alignment, translation fidelity)
- Section 9: Failure Modes & Fixes (6 named failure modes: register bleed-through, gap-fill overload, translation betrayal, onomatopoeia literalization, cascade collapse, register contamination)
- Section 10: Quick Reference Card

**Open item on Protocol 02:** Robert was running experiments — same task with compressed native-register prompt vs. verbose polite prompt, comparing output tone, formality, sentence rhythm. Failure Mode section is marked for verification against experimental data. No rewrite needed; just add examples if/when collected.

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
| 2 | Push README + Protocol 01 + Protocol 02 | 15 min | ⬜ Not started (files are ready) |
| 3 | Configure GitHub Pages | 15 min | ⬜ Not started |
| 4 | **Write Protocol 02** (Japanese AI Interaction Guide) | 4–6 hrs | ✅ Complete |
| 5 | Write Protocol 03 (Multilingual Research Synthesis) | 3–4 hrs | ⬜ Not started |
| 6 | Write Protocol 04 (System Discovery & Implementation) | 3–4 hrs | ⬜ Not started |

---

## Protocol 03 — Multilingual Research Synthesis (next up)

From PRD Section 4: *Synthesizing sources across 2+ languages without translation-flattening.*

No deliberation has happened yet on this protocol. Start with design conversation before writing.

Key questions to answer before writing:
- What does "translation-flattening" mean operationally, and what are its observable symptoms?
- What are the distinct failure modes when synthesizing across 2+ languages?
- Does this protocol assume the user reads all the source languages, or some subset?
- What is the output format — a single synthesis document, a side-by-side, or something else?
- What's the research backing for this protocol (parallel to Hall + Shibatani for Protocol 02)?

---

## Open questions

| Question | Status |
|---|---|
| GitHub username — needs to appear in repo URL and README footer | ⬜ Resolve before pushing |
| Protocol 02 failure mode verification — experimental data from prompt comparison experiments | ⬜ Robert collecting; no rewrite needed until data is in hand |

---

## Files to push to GitHub (when ready)

```
README.md
protocols/01-study-guide-builder.md
protocols/02-japanese-ai-interaction-guide.md
```

All three are clean and public-ready. No proprietary references. Verified.

---

## To resume in a new session

Say: **"I'm continuing the AI Protocol Library project. Read the HANDOFF.md in the ai-protocol-library folder."**

**Next steps in order:**
1. Create GitHub repo + push README and both protocols (15–30 min, Robert does this manually)
2. Configure GitHub Pages (15 min, Robert does this manually)
3. Design deliberation for Protocol 03 (Multilingual Research Synthesis) — answer the open questions above before writing
4. Write Protocol 03

The PRD is at `/mnt/showcase/AI_Protocol_Library_PRD.docx` if deeper context is needed.
