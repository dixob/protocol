# Session Handoff — AI Protocol Library

**Project:** ai-protocol-library (Portfolio Project 6)
**Last updated:** 2026-03-10
**Status:** Protocol 02 deliberation in progress. Compression catalog collected. Failure modes pending experiments. Two deliberation questions remaining.

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
| 4 | **Write Protocol 02** (Japanese AI Interaction Guide) | 4–6 hrs | 🔄 In progress — deliberation done, writing not started |
| 5 | Write Protocol 03 (Multilingual Research Synthesis) | 3–4 hrs | ⬜ Not started |
| 6 | Write Protocol 04 (System Discovery & Implementation) | 3–4 hrs | ⬜ Not started |

---

## Protocol 02 — what needs to be written

This is the most original and differentiating protocol in the library. It covers how to interact with AI systems in Japanese — specifically the patterns used by professional Japanese AI practitioners that differ from the "polite verbose" approach many tools default to.

### Decisions made (this session)

| Decision | Resolution |
|---|---|
| Attribution framing | "Direct practitioner observation" + linguistic backing. Do not name company. |
| Examples location | Inline in the .md file — portability/deployability wins over modularity |
| Example outputs | Constructed, purpose-built to show contrast clearly |
| GitHub push | Robert will push manually |

### Core sections to write:

**Register Selection Framework** — When to use which register:
- 丁寧語 (polite/desu-masu) — general use, first contact
- 普通体 (plain form) — iterative work, efficiency-focused
- 命令形 (imperative/command form) — task execution, the "expert mode"

The protocol needs to explain *why* each register produces different AI behavior, not just when to use it. Core argument: models trained on native Japanese text have learned that terse, context-dependent input correlates with expert-level interaction. Verbose/hedged input pattern-matches to beginner or non-native usage, and the model mirrors that register back.

**Compression Pattern Catalog** — 5 practitioner examples collected, 6 underlying patterns identified. All examples follow Expert (1) vs. Non-native/beginner (2) format.

*Collected examples:*

1. Document creation
   - Expert: `資料作成：ｘｙｚ。Handoff.md参考にして`
   - Beginner: `Handoff.mdを見てこのドキュメントを作ってください。ｘｙｚをカバーしてください。`

2. Medical/advice
   - Expert: `頭痛い、右側、ジンジン、どうして？`
   - Beginner: `昨日からずっと頭の右側が痛いです。理由は何ですか？`

3. Email reply
   - Expert: `メール返信手伝って。内容：ｘｙｚ、言いたいこと：ｘｙｚ`
   - Beginner: `このメールが送られてきました：ｘｙｚ。返信を返すのに手伝ってください。私はｘｙｚを伝えたいです。どのように書いたらいいですか？`

4. Technical / PR creation
   - Expert: `PR作ってこのバグ直して。[link]`
   - Beginner: `このコードベースでバグがありました。（リンク）PRを作成して、修正をしてください。`

5. Research summary
   - Expert: `AIツール、最近のニュース、まとめて`
   - Beginner: `新しいAIツールのリサーチがしたいです。最近出てきたAIツールをリサーチして、サマリーを作ってください。`

6. Original example (from prior session)
   - Expert: `展開して。NPMとかYarnでできそう。`

*6 underlying patterns extracted:*
1. **Noun-label framing** — task structured as labeled fields (資料作成：, 内容：, 言いたいこと：), not narrative sentences
2. **Te-form as bare command** — 参考にして, 手伝って, まとめて without ください; often chained (作って直して)
3. **Fragment + comma syntax** — comma-separated sensory/topical fragments; onomatopoeia as precision (ジンジン)
4. **Context-as-pointer** — hyperlink or file reference IS the context; model trusted to read it without narration
5. **Single verb, multiple actions** — verb selection carries the full task (まとめて = research + synthesize + output)
6. **Dialogue assumption** — prompts are intentionally lean; incomplete information is fine because follow-up is expected; high-context communication norm applied to AI interaction

**Evaluation Rubric / Failure Modes** — ⚠️ PLACEHOLDER. Robert is running experiments to surface real examples of AI Japanese output that is grammatically correct but stylistically off.

*Experiment design agreed:* Run same task with compressed native-register prompt vs. verbose polite prompt. Compare output tone, formality, sentence rhythm, idiomaticity. Good task types: business email reply, document summary, short technical explanation. Avoid tasks where correctness dominates over style.

*What to look for:* over-use of ので/ため, excessive nominalization (〜すること), uniform keigo where a native writer would shift register, unnaturally explicit subject-object chains.

*Fill this section in before writing the protocol.*

**Bilingual Switching Logic** — ⚠️ DELIBERATION IN PROGRESS (Q3 not yet discussed).

Key practitioner observation already captured: prompting in Japanese when output should be in Japanese produces better results than prompting in English + requesting translation. The language of the instruction affects the language of the reasoning, not just the output. Full rules to be explored next session.

**Activation Pattern** — ⚠️ DELIBERATION IN PROGRESS (Q4 not yet discussed).

Question: does Robert use a specific session-opening pattern to signal to the AI that he wants native-register Japanese output? To be explored next session.

### Research backing (to cite in the protocol):
- Edward T. Hall, *Beyond Culture* (1976) — high-context/low-context communication framework. Japanese is the canonical example.
- 省略 (grammatical ellipsis) and 文脈依存性 (context dependency) are well-documented Japanese linguistic features. Shibatani's *The Languages of Japan* covers ellipsis substantively.
- Frame the Japan observations explicitly as practitioner-sourced from direct observation and linguistic context. This framing is honest and more credible to a technical reader than a survey.

### On expanding beyond anecdote:
There are no publicly available LLM datasets that are useful for this specific claim — WildChat, LMSYS, ShareGPT exist but are English-dominant and have no native speaker/cultural metadata. The right approach is:
1. Cite existing linguistic literature (Hall, Shibatani) for the underlying phenomenon
2. Source naturalistic examples from Qiita, Zenn, and Twitter/X (`#プロンプト`, `#プロンプトエンジニアリング`)
3. Frame the protocol as practitioner research explicitly — this is a strength, not a gap

---

## Open questions

| Question | Status |
|---|---|
| GitHub username — needs to appear in repo URL and README footer | ⬜ Resolve before pushing |
| GenerativeX attribution — how explicit to be in Protocol 02? | ✅ Resolved — "direct practitioner observation" + linguistic backing. No company name. |
| Japanese examples in Protocol 02 — inline or separate examples/ directory? | ✅ Resolved — inline, for portability/deployability |
| Real vs. constructed example outputs in Protocol 02? | ✅ Resolved — constructed, purpose-built for contrast |
| Failure mode examples — need real data | ⚠️ Robert running experiments. Fill in before writing. |
| Bilingual switching logic — full rule set | ⬜ Deliberation Q3, not yet discussed |
| Activation pattern — does one exist? | ⬜ Deliberation Q4, not yet discussed |

---

## Files to push to GitHub (when ready)

```
README.md
protocols/01-study-guide-builder.md
```

These are clean and public-ready. No proprietary references. Verified.

---

## To resume in a new session

Say: **"I'm continuing the AI Protocol Library project. Read the HANDOFF.md in the ai-protocol-library folder."**

**Next steps in order:**
1. Share failure mode examples from experiments (fill in the Evaluation Rubric section above)
2. Complete deliberation Q3 — bilingual switching logic
3. Complete deliberation Q4 — activation pattern
4. Write Protocol 02

The PRD is at `/mnt/showcase/AI_Protocol_Library_PRD.docx` if deeper context is needed.
