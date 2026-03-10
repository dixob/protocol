# Protocol 02 — Japanese AI Interaction Guide

> **Status:** ✅ Available
> **Audience:** AI practitioners working in Japanese-language contexts — developers, consultants, researchers, and knowledge workers using AI tools for Japanese-language tasks.
> **What makes this different:** This protocol documents compression patterns observed in professional Japanese AI usage that are not documented in any English-language prompting resource at this level of specificity.

---

## Part 1: User Instructions

**Load this protocol into a new AI session, then follow these five steps:**

1. **Set your working language before starting.** Open the session in the language you want to receive output in. Japanese output → start in Japanese. English output → start in English.

2. **Choose your register.** Use the Register Selection Table (Section 3) to select 丁寧語, 普通体, or 命令形 based on your task and output requirements.

3. **Apply compression patterns.** Use the Compression Pattern Catalog (Section 4) to write efficient, expert-register prompts. Each pattern shows an expert form and a novice form with explanation.

4. **Activate expert mode if needed.** Use an Activation Pattern (Section 6) to explicitly establish session register before starting work. Required for new sessions; optional for advanced practitioners.

5. **Evaluate your output.** Use the Evaluation Rubric (Section 8) to assess whether the output matches the register, naturalness, and fidelity you need.

---

## Part 2: Operational Specification

*This section is the operational specification for this protocol. It is written as a direct instruction set for an AI system, but is fully readable by a human practitioner who wants to understand what the protocol is doing and why.*

---

### Section 1: Operational Protocol

#### 1.1 Trigger Conditions

Activate this protocol when:
- The desired output is in Japanese
- The task involves AI-assisted Japanese writing, editing, translation, or localization
- You want to use compressed, expert-register prompting to improve output quality
- You are evaluating whether AI Japanese output is natural for a native reader
- You are building AI-assisted workflows for a Japanese-language product or professional context

#### 1.2 What This Protocol Produces

When followed, this protocol produces AI output that:
- Matches the requested formality level (register accuracy)
- Sounds natural to a native Japanese reader — not translated or rendered from English
- Preserves nuance in translation and localization tasks
- Responds to compressed prompts without filling in assumed gaps

#### 1.3 What This Protocol Does Not Cover

- Machine translation quality comparison across systems
- Japanese language learning or grammar instruction
- Japanese-specific AI model recommendations (Rinna, Japanese-BERT, etc.)
- Romanization, transliteration, or furigana handling
- SEO or marketing copy optimization in Japanese

---

### Section 2: The Core Insight

#### 2.1 The Expert/Novice Divergence

In Japan's professional AI user community, the highest-competency users do not write polite, formal prompts. They write terse, compressed, command-line-style instructions that assume high context.

This pattern was observed across multiple field delivery engineers (FDEs) and developer advocates at a Japan-market AI consulting firm. It represents a distinct competency gap between casual AI users and professional AI practitioners in the Japanese market — and it is not documented in any English-language prompting resource at this level of specificity.

The divergence looks like this:

| Competency level | Prompt style | Example |
|---|---|---|
| Non-native / beginner | Verbose, polite, narrative | 新しいAIツールのリサーチがしたいです。最近出てきたAIツールをリサーチして、サマリーを作ってください。 |
| Native casual | Conversational, moderate compression | 最近のAIツールをまとめてほしい |
| Expert practitioner | Terse, compressed, field-labeled | AIツール、最近のニュース、まとめて |

#### 2.2 Why This Produces Different Output

Language models trained on native Japanese text have learned that terse, context-dependent input correlates with expert-level interaction. Verbose, hedged input pattern-matches to non-native or beginner usage, and models tend to mirror the register of the input back in the output.

When you write a polite, over-specified prompt in Japanese, the model infers it is talking to someone who needs guidance. It responds with more scaffolding, more explanation, more hedging. When you write a compressed, expert-register prompt, the model infers it is in an expert-to-expert exchange and responds accordingly: direct, dense, efficient.

This is not a prompt-engineering trick. It is the same phenomenon that shapes how a Japanese native speaker writes differently to a senpai than to a kouhai — the register of the input frames the entire interaction.

#### 2.3 Linguistic Grounding

This behavior is supported by documented features of the Japanese language:

**High-context communication** (Hall, *Beyond Culture*, 1976): Japanese is the canonical example of a high-context culture. Meaning is carried by shared context, not explicit statement. Grammatically incomplete utterances are not ambiguous — they are precise, because the context they depend on is assumed to be shared.

**省略 (grammatical ellipsis) and 文脈依存性 (context dependency)**: Subject-drop, object-drop, and verb-drop are grammatical features of Japanese, not informal shortcuts. A model trained on native Japanese text has learned that these omissions are normal and intended. (Shibatani, *The Languages of Japan*, 1990)

The implication: prompting in expert-register Japanese is not "incomplete" — it is correctly calibrated for high-context communication. Non-native verbosity is the deviation, not the norm.

---

### Section 3: Register Selection Framework

#### 3.1 The Three Registers

Japanese has distinct grammatical registers with different implications for AI interaction.

| Register | Form | Signal to the model | Typical output |
|---|---|---|---|
| **丁寧語** (polite) | です・ます form | General use, first contact, formal context | Formal, scaffolded, explanatory |
| **普通体** (plain form) | Dictionary form + だ | Efficiency-focused, iterative work, internal documents | Neutral, efficient, peer-register |
| **命令形** (imperative/command) | Bare verb or te-form without ください | Task execution, expert mode | Direct, dense, execution-focused |

#### 3.2 Register Selection Table

| Task type | Output register needed | Recommended input register |
|---|---|---|
| First message in a new session | Any | Match desired output |
| Iterative task refinement | Any | 普通体 or 命令形 |
| Business email drafting | 丁寧語 | 普通体 (describe the task; let the model handle the output register) |
| Technical documentation | Formal 普通体 | 普通体 |
| Internal notes / summaries | 普通体 | 命令形 |
| Code-related tasks | N/A | 命令形 |
| Translation or localization | Match target audience | See Section 5 (Bilingual Switching Logic) |
| Diagnosis / problem-solving | Any | Fragment + comma syntax (see Pattern 3) |

#### 3.3 Why Register Selection Matters

The critical principle: **the register of your input shapes the register of the AI's reasoning, not just its output.** When you prompt in 丁寧語, the model enters formal explanation mode. When you prompt in 命令形, it enters execution mode. For tasks where you want dense, efficient work — code, summarization, structured drafting — execution mode produces better results.

---

### Section 4: Compression Pattern Catalog

*Each entry shows the expert form and the novice form, explains what is omitted and why it is safe to omit, and specifies when each pattern is and is not appropriate.*

---

#### Pattern 1: Noun-Label Framing

**What it is:** Task parameters structured as labeled fields, not narrative sentences.

| Form | Example |
|---|---|
| Expert | `資料作成：xyz。Handoff.md参考にして` |
| Novice | `Handoff.mdを見てこのドキュメントを作ってください。xyzをカバーしてください。` |

**What is omitted:** The request verb (implied by the label), the scope declaration, all politeness endings.

**Why it is safe to omit:** The label (`資料作成：`) carries the task type. The model reads the colon-formatted label as a task declaration. The file reference with bare te-form (`参考にして`) is grammatically complete as a command.

**When to use:** Any structured task with multiple parameters — document creation, analysis requests, content generation with defined constraints.

**When not to use:** When the relationship between parameters is not obvious (e.g., parameter A must take priority over parameter B in ways the model won't infer from position alone).

---

#### Pattern 2: Te-form as Bare Command

**What it is:** Using the て-form verb without ください, often chained for sequential tasks.

| Form | Example |
|---|---|
| Expert | `メール返信手伝って。` |
| Novice | `メールの返信をするのを手伝ってもらえますか？` |
| Chained | `PR作ってこのバグ直して。` |

**What is omitted:** ください, もらえますか, the full request scaffold.

**Why it is safe to omit:** Te-form is grammatically complete as a request in natural Japanese. The politeness marker ください is additive, not required for clarity. Omitting it changes register, not meaning.

**When to use:** All task requests in iterative work sessions. Default pattern for 命令形 register.

**When not to use:** Chained commands where order matters or where the two actions have a dependency relationship. ⚠️ See Failure Mode 5 (Cascade Collapse) — number sequential tasks explicitly if one must complete before the other.

---

#### Pattern 3: Fragment + Comma Syntax

**What it is:** Comma-separated topical fragments, including onomatopoeia as precision descriptors.

| Form | Example |
|---|---|
| Expert | `頭痛い、右側、ジンジン、どうして？` |
| Novice | `昨日からずっと頭の右側が痛いです。理由は何ですか？` |

**What is omitted:** Tense markers, full sentence structure, copula, temporal framing.

**Why it is safe to omit:** Each fragment carries a distinct piece of diagnostic information. The model processes these as a constraint set, not a story to decode. Onomatopoeia (ジンジン) is a precision descriptor — it communicates sensation quality that a full sentence would over-specify or flatten.

**When to use:** Diagnosis, description, sensory or symptomatic input. Any task where you are providing signal, not narrating.

**When not to use:** When temporal or causal relationships between the fragments are the task itself (e.g., 昨日の会議が原因で… requires the causal chain to be stated explicitly).

---

#### Pattern 4: Context-as-Pointer

**What it is:** A hyperlink or file reference serves as the complete context. The model is trusted to read it without narration.

| Form | Example |
|---|---|
| Expert | `PR作ってこのバグ直して。[link]` |
| Novice | `このコードベースでバグがありました。（リンク）PRを作成して、修正をしてください。` |

**What is omitted:** Description of what the link contains, the stated relationship between the link and the task.

**Why it is safe to omit:** The model can read the linked material. Narrating the context before providing the link is redundant — and signals that you don't trust the model to read it. Expert mode: provide the pointer, then the task.

**When to use:** Any task where the model can access the linked content and where the relevant aspect is implied by the task verb.

**When not to use:** When the specific aspect of the context you care about isn't obvious from the link alone (e.g., you want the model to focus on a specific section of a long document — specify it).

---

#### Pattern 5: Single-Verb Task Compression

**What it is:** Selecting a verb that implies the full task pipeline — research, synthesize, and format in one word.

| Form | Example |
|---|---|
| Expert | `AIツール、最近のニュース、まとめて` |
| Novice | `新しいAIツールのリサーチがしたいです。最近出てきたAIツールをリサーチして、サマリーを作ってください。` |

**What is omitted:** The meta-description of the task (I want to research...), the explicit summarize instruction, the output format spec.

**Why it is safe to omit:** `まとめて` carries the full pipeline: find relevant information, synthesize it, produce a summary. The verb selection is the spec.

**Useful single-verb task compressions:**

| Verb | Implied pipeline |
|---|---|
| `まとめて` | Research + synthesize + output summary |
| `整理して` | Organize, structure, or clean up existing material |
| `確認して` | Check, verify, or review for accuracy |
| `展開して` | Expand on, elaborate, or build out |
| `絞って` | Narrow down, filter, reduce to essentials |

**When to use:** Tasks where the desired output format is implied by the verb. Add a format constraint if needed: `まとめて。箇条書き、5点。`

**When not to use:** When the output format is non-obvious or when the pipeline implied by the verb doesn't match what you want. Add explicit constraints rather than choosing a different approach.

---

#### Pattern 6: Dialogue Assumption

**What it is:** Prompts are intentionally incomplete, with the expectation that follow-up exchange will resolve gaps.

| Form | Example |
|---|---|
| Expert | `展開して。NPMとかYarnでできそう。` |

**What is happening:** No subject, no object — the referent is assumed from prior conversation context. The second sentence is a working hypothesis, not a specification.

**What is omitted:** The full specification of what to expand, confirmation of which tool to use, expected output format.

**Why it is safe to omit:** In high-context communication, incomplete information is resolved through dialogue. The practitioner expects the model to respond with the most reasonable interpretation and flag if clarification is needed. This is a feature, not a gap.

**When to use:** Iterative sessions where context has been established in prior turns. There must be something in the conversation history to point at.

**When not to use:** Opening message of a new session. Dialogue assumption requires an established context — this pattern fails cold.

---

#### Pattern 7: Language-of-Output-First

**What it is:** Opening the session in the language you want to receive output in.

| Form | Approach |
|---|---|
| Expert | Open the session in Japanese when the desired output is Japanese |
| Non-expert | Open in English + add "please respond in Japanese" |

**What this achieves:** The instruction language shapes the reasoning chain, not just the surface output. When you prompt in Japanese, the model reasons in Japanese. When you prompt in English and request Japanese output, the model may internally reason in English and translate — producing output that sounds rendered rather than native.

**When to use:** Any session where the primary output language is Japanese.

**When not to use:** When you are providing substantial English source material that requires English-language processing first (technical documentation, English-language research). In this case, use Activation Pattern B (Section 6) to establish the output language explicitly while keeping context-setting in English.

---

#### Pattern 8: Rebuild Over Translate

**What it is:** Instructing the model to produce a Japanese-native version from scratch using the source as reference, rather than translating the source directly.

| Form | Instruction |
|---|---|
| Expert | `英語版を翻訳するんじゃなくて、日本語版を同じコンテンツで一から作り直して。` |
| Standard | `日本語に翻訳して。` |
| Non-expert | "Translate this to Japanese." |

**What changes:** The model is instructed to treat the English as reference material, not as syntax to remap. The output is Japanese in structure and flow — not English-shaped.

**When this matters:** When natural Japanese output is more important than literal fidelity to the source. Business communications, creative content, marketing copy, game dialogue. Any case where a Japanese-native writer would make structurally different choices than an English-native writer.

**When to use literal translation instead:** Legal, technical, or contractual text where every clause of the original must be preserved. Medical instructions where precision overrides naturalness.

---

### Section 5: Bilingual Switching Logic

*When to switch languages, and how to do it cleanly.*

#### Rule 1: Match Language to Output

Start the session in the language you want to receive output in. This is the single most important rule for language calibration.

- Want Japanese output → start in Japanese
- Want English output → start in English
- Want bilingual output → complete one version fully; rebuild the second separately (see Rule 4)

#### Rule 2: Mid-Session Switch for Translation Tasks Only

Switch languages mid-session only when producing a translated version is the explicit task. Switching for any other reason creates register ambiguity that degrades output quality across subsequent turns.

#### Rule 3: Translate in the Target Language

When requesting translation, prompt in the target language rather than the source language.

| Form | Instruction |
|---|---|
| Preferred | `日本語に翻訳して。` |
| Less effective | "Translate this to Japanese." |

The Japanese instruction keeps the model operating in Japanese rather than cross-processing: receiving an English instruction and then executing a Japanese task.

#### Rule 4: For Natural Output — Rebuild, Don't Translate

When naturalness matters more than fidelity, use the rebuild instruction:

```
英語版を翻訳するんじゃなくて、日本語版を同じコンテンツで一から作り直して。
```

This instructs the model to treat the source as reference material, not source text. The output will be Japanese-native in structure and phrasing rather than English-shaped.

---

### Section 6: Activation Patterns

*How to establish session register before starting work.*

Activation patterns are session-opening instructions that calibrate the AI to expert-register Japanese mode before any task begins. Use them when you need to establish the register explicitly — rather than relying on the first task message to set it implicitly.

---

#### Pattern A — Self-Exemplifying Register Declaration

*For new Japanese sessions.*

```
作業言語：日本語。敬語不要。簡潔に。
```

**Why this works:** The instruction is itself written in the target register — noun-label framing, no politeness markers, minimal. The model calibrates from the opening message because the meta-instruction demonstrates the style it requests.

**Use when:** Opening a dedicated Japanese-language session where the task is Japanese from start to finish.

---

#### Pattern B — English Meta-Instruction for Japanese Output

*For sessions with English source material.*

```
Working language: Japanese. Native register. No keigo. Compress responses.
```

**Why this works:** When providing English source material (documentation, research, code), English context-setting is appropriate. The explicit meta-instruction establishes that output should be in Japanese, native-register, before any content is provided.

**Use when:** You are providing English materials as context and want Japanese output. The session is bilingual by nature.

---

#### Pattern C — Implicit Activation

*For advanced practitioners.*

No activation statement. Open the first message in expert-register Japanese — the model mirrors the register.

**Why this works:** Language models mirror the register of the input. A first message in compressed 命令形 signals expert-level interaction from the first token.

**Risk:** If the model defaults to keigo on the first response, you spend a turn correcting it. In time-sensitive or high-stakes work, use Pattern A instead.

**Use when:** You are confident in reading and correcting a register mismatch on first output. This is mastery-level usage, not the default recommendation.

---

### Section 7: Translation Context Module

*For AI-assisted translation and localization, especially Japanese ↔ English.*

#### 7.1 When to Prompt in Source vs. Target Language

| Situation | Recommended approach |
|---|---|
| Output should be Japanese-native | Prompt in Japanese; use rebuild pattern if source exists |
| Output requires literal source fidelity | Prompt in Japanese; use `翻訳して` without rebuild instruction |
| Complex English source + Japanese output | Prompt in English (Pattern B); switch to Japanese for the translation step |
| Bilingual document (both versions needed) | Complete one version fully first; rebuild the second separately |

#### 7.2 Translation vs. Localization

AI handles these two tasks differently and conflates them without clear instruction.

**Translation** preserves the source text's meaning, structure, and tone as closely as possible. This is what the model does by default when given a translation instruction.

**Localization** adapts content for the target culture — structure, idiom, cultural references, and register may all shift. Requires explicit instruction.

To request localization rather than translation:

```
翻訳じゃなくて、日本のユーザー向けに自然な形でローカライズして。
```

#### 7.3 Common Failure Modes in Japanese Game Localization

*From direct QA experience with JP-EN game localization.*

**Honorific collapse**
Japanese character relationships are expressed through honorifics (先輩/後輩, さん/くん/ちゃん, keigo between characters of different status). English has no structural equivalent. Without instruction, AI defaults to flattening all character-to-character dialogue to the same register, erasing relationship dynamics.

*Fix:* Include a relationship map in the translation brief (see 7.4). Specify per-character register rules: `Player character speaks to Aria in casual form. Aria speaks to player in polite form.`

**Gender ambiguity collapse**
Japanese is largely gender-neutral at the sentence level — 彼/彼女 appear less frequently than English she/he. AI translating JP→EN often defaults to gendered pronouns when the Japanese was intentionally ambiguous.

*Fix:* Include a gender neutrality policy in the brief: `Avoid gendered pronouns for [character] unless dialogue explicitly indicates gender. Use "they/them" or restructure to avoid the pronoun.`

**NPC register normalization**
Game NPCs often speak in stylized registers that signal personality — archaic, curt, eccentric, childlike. AI tends to normalize NPC dialogue to standard modern Japanese or standard English, erasing characterization.

*Fix:* Provide one confirmed example of the NPC's register as an anchor: `This character speaks in archaic 候文 style. Reference: [example line]. Maintain this register throughout.`

**Cultural reference handling**
References to Japanese cultural practices (花見, 文化祭, etc.) require a policy decision: adapt (replace with equivalent), annotate (add explanatory note), or preserve (leave as-is). Without instruction, AI defaults to over-explanation or silent omission.

*Fix:* State the policy in the brief: `Cultural references: preserve. Do not add explanatory notes. Treat the reader as familiar with the reference.`

#### 7.4 Translation Brief Pattern

A translation brief is a structured instruction provided before the translation task. It constrains the model to the correct register, audience, and handling policies. Include it as the first message in any translation session.

```
翻訳対象：[content type — e.g., キャラクターダイアログ, 製品説明, ゲームUI]
方向：[EN→JP / JP→EN]
対象読者：[e.g., 日本のゲームプレイヤー、20代〜30代]
トーン：[e.g., カジュアル / 専門的 / キャラクター特有]
固有名詞：[keep / translate / annotate]
文化参照：[preserve / adapt / annotate]
敬語方針：[localize / preserve / flatten]
キャラクター関係：[optional — describe key register relationships]
参考文体：[optional — provide 1–2 confirmed lines as register anchor]
```

---

### Section 8: Evaluation Rubric

*Use this rubric to assess whether AI Japanese output meets the standard for your task.*

Four dimensions. Each scored **pass** or **needs revision**.

---

#### Dimension 1: Register Accuracy

**Question:** Does the output match the requested formality level?

| Pass | Needs revision |
|---|---|
| Output uses the register specified throughout | Output defaults to keigo when 普通体 or 命令形 was requested |
| Register is consistent across the full output | Register shifts mid-document without cause |
| Business email uses 丁寧語; internal note uses 普通体 | Business email contains casual て-form connectors mid-body |

**Signal to watch:** The first sentence sets the register. If the opening is wrong, the rest usually is too.

---

#### Dimension 2: Compression Integrity

**Question:** Did compressing the prompt cause any loss of instruction fidelity?

| Pass | Needs revision |
|---|---|
| All parameters from the prompt appear in the output | The model filled a gap with something not intended |
| The verb's implied pipeline matches what was received | A task step was dropped or silently replaced |
| Follow-up questions from the model are precise | Generic clarifying question rather than execution |

**Signal to watch:** Unexpected additions or missing steps. If the output contains something you didn't ask for, or is missing something you implied, the compression lost a constraint. Add an explicit label (Pattern 1) to the next attempt.

---

#### Dimension 3: Cultural Register Alignment

**Question:** Would a Japanese reader find this output natural for its stated purpose?

| Natural output | Rendered output |
|---|---|
| Sentence-final forms vary appropriately (ね、よ、か) | All sentences end in identical form (です. or ます.) |
| Topicalization (は vs が) reflects information structure | Subject-object-verb chain reads like translated syntax |
| Connectors are idiomatic (それに、ただ、つまり) | Over-use of ので and ため for all causal relationships |
| Relative clauses are compact | Nominalization overuse (〜することが重要です repeatedly) |

**If you are not a native reader:** Flag cultural register alignment as provisional and have a native speaker review before publishing or sending. This dimension is the hardest to evaluate without fluency.

---

#### Dimension 4: Translation Fidelity (if applicable)

**Question:** Does the output preserve nuance, not just literal meaning?

| Pass | Needs revision |
|---|---|
| Character relationships preserved (honorific mapping intact) | All dialogue flattened to the same register |
| Intentional ambiguity preserved | Gendered pronouns added where source was ambiguous |
| Cultural references handled per brief policy | Reference over-explained, adapted without instruction, or dropped |
| Tone and personality of source are recognizable | NPC voice normalized to standard register |

---

### Section 9: Failure Modes & Fixes

*Named failure modes with symptoms, root causes, and specific corrections.*

*Note: These failure modes are derived from documented LLM behavior patterns and practitioner observation. They are marked for ongoing verification through comparative experiment: same task run with compressed native-register prompt vs. verbose polite prompt, comparing output tone, formality, sentence rhythm, and idiomaticity.*

---

#### Failure 1: Register Bleed-Through

**Symptom:** You prompted in 命令形 or 普通体 and the output opens with ご質問ありがとうございます or is written entirely in です・ます form.

**Root cause:** The model's politeness defaults override the register signal when the signal is not explicit enough. Common in the first turn of sessions where no Activation Pattern was used.

**Fix:** Add explicit declaration to the opening message: `敬語不要。` Or use Activation Pattern A at session start. If it happens mid-session, correct with: `以降、普通体で。敬語なし。`

---

#### Failure 2: Gap-Fill Overload

**Symptom:** You wrote a compressed prompt (e.g., `まとめて`) and received two paragraphs of methodology scaffolding before the actual content. The model is producing output you didn't ask for.

**Root cause:** Minimal input is interpreted as uncertainty. The model fills inferred gaps with scaffolding — explaining what it is about to do before doing it, or adding caveats around the requested content.

**Fix:** Add an output format constraint. `まとめて。箇条書き。5点。` The format spec signals that you want content, not process. Alternatively: `前置き不要。結果だけ。`

---

#### Failure 3: Translation Betrayal

**Symptom:** The Japanese output is grammatically correct but sounds rendered — unusual topic ordering, explicit subject-object chains (彼が彼女に本を渡した rather than simply 渡した), over-use of nominalizations (〜することが重要です).

**Root cause:** The model reasoned internally in English and translated. This is common when the session was opened in English or when English source material dominated the context window.

**Fix:** Use the rebuild pattern:
```
英語版を翻訳するんじゃなくて、日本語版を同じコンテンツで一から作り直して。
```
Alternatively, start a fresh session in Japanese (Pattern 7) and provide the English source as reference material only.

---

#### Failure 4: Onomatopoeia Literalization

**Symptom:** You used an onomatopoeia as a precision descriptor (e.g., ジンジン in a symptom prompt) and the model explained the word rather than used it as a calibration signal.

**Root cause:** Onomatopoeia appears less frequently in formal training data. When the model encounters it in an otherwise sparse prompt, it may treat it as a word requiring explanation rather than a descriptor to apply.

**Fix:** Follow the fragment with an explicit suppression instruction: `ジンジン、説明不要。症状の可能性を挙げて。` Or establish the fragment + comma pattern earlier in the session with a simpler example before using onomatopoeia.

---

#### Failure 5: Cascade Collapse

**Symptom:** You chained two commands (e.g., `PR作ってこのバグ直して`) and only one task was completed.

**Root cause:** Token-by-token generation treats each command independently. When the first command produces substantial output, the second command is dropped or treated as a separate, unexecuted instruction.

**Fix:** If the tasks are sequential or dependent, number them explicitly:
```
1. バグ修正
2. PR作成。
```
This makes execution order and scope unambiguous. Reserve te-form chaining for truly parallel tasks with no dependency.

---

#### Failure 6: Register Contamination

**Symptom:** Output mixes registers within a single document — some sentences in keigo, others in plain form — without apparent reason.

**Root cause:** The model is not maintaining register consistency across a long output. Most common in documents that span multiple sections or were generated in parts.

**Fix:** Add a register consistency constraint at the task start: `全体を通して普通体で統一。` For business documents: `全文、丁寧語で統一。` Spot-check the first and last paragraphs — if they match, the middle usually does too.

---

### Section 10: Quick Reference Card

```
REGISTER SELECTION
─────────────────────────────────────────────────────
丁寧語      First contact, formal, business-facing output
普通体      Iterative work, internal docs, peer register
命令形      Task execution, code, expert mode

ACTIVATION PATTERNS
─────────────────────────────────────────────────────
New JP session:   作業言語：日本語。敬語不要。簡潔に。
English source:   Working language: Japanese. Native register. No keigo.
Advanced:         Open in target register — no activation needed

BILINGUAL SWITCHING
─────────────────────────────────────────────────────
Default:          Start in desired output language
Translation:      日本語に翻訳して。  (not "translate to Japanese")
Natural output:   英語版を翻訳するんじゃなくて、
                  日本語版を同じコンテンツで一から作り直して。

COMPRESSION PATTERNS
─────────────────────────────────────────────────────
1. Noun-label       資料作成：xyz。[file]参考にして
2. Te-form command  手伝って / 作って直して / まとめて
3. Fragment+comma   頭痛い、右側、ジンジン、どうして？
4. Context-pointer  タスク説明。[link]
5. Single-verb      まとめて / 整理して / 展開して / 絞って
6. Dialogue assume  展開して。NPMとかYarnでできそう。
7. Language-first   Open the session in the target language
8. Rebuild          英語版を翻訳するんじゃなくて、
                    日本語版を一から作り直して。

FAILURE SIGNALS
─────────────────────────────────────────────────────
Keigo when not asked   →  敬語不要。at session start
Verbose scaffolding    →  前置き不要。結果だけ。+ format spec
Sounds translated      →  Rebuild pattern; fresh JP session
Register inconsistent  →  全体を通してXXで統一。
Cascade dropped        →  Number sequential tasks explicitly
```

---

*Protocol 02 — Japanese AI Interaction Guide*
*AI Protocol Library | github.com/[username]/ai-protocol-library*
*Sources: Hall, E.T. (1976). Beyond Culture. Shibatani, M. (1990). The Languages of Japan. Compression patterns: practitioner observation, Japan-market AI consulting context.*
