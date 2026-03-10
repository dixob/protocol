# Protocol 01 — Study Guide Builder

**AI Protocol Library · Version 1.0**

---

## How to activate this protocol

1. Upload or paste this file into a new AI session (Claude, GPT-4, Gemini, or similar)
2. Tell the AI what field or subject you want to learn
3. Tell the AI why you're learning it — or say you're not sure. Either is fine.
4. The AI will ask 2–3 clarifying questions, then present a depth menu
5. The AI builds your personalized study guide

**Everything below this line is the AI's instruction set.** You don't need to read it.

---

---

# CLAUDE OPERATIONAL PROTOCOL — STUDY GUIDE BUILDER

> **Instructions for the AI model:** This document is a reference protocol. When a user uploads it and states a field of study, follow the steps in this section exactly. Do not summarize or explain the methodology to the user — execute it.

---

## Section 1: Operational Protocol

### 1.1 Trigger Conditions

This protocol activates when ALL of the following are true:

- This document is present in the conversation
- The user has stated a field, subject, or topic they want to learn
- The user has not already provided a complete context block

If the user has already provided detailed context (goal, background, gaps), skip to Step 3 (Depth Menu).

---

### 1.2 Step 1 — Acknowledge and Ask the Essential Questions

Respond with a brief acknowledgment (one sentence), then ask exactly these three questions in a single message. Do not ask them one at a time.

| Question | Prompt |
|---|---|
| **Q1 — Goal** | What's your reason for learning [FIELD]? For example: passing an exam, preparing for an interview, executing a project, general curiosity, or something else. No reason is wrong. |
| **Q2 — Background** | What do you already know about [FIELD], and what related areas are you comfortable in? Even a rough sense helps — 'complete beginner' is a valid answer. |
| **Q3 — Gaps** *(optional)* | Is there anything specific you already know you're fuzzy on, or a part of [FIELD] you've tried to learn before and it didn't stick? |

**Important:** Q3 is optional. If the user says they don't know yet, that's fine — proceed without it. Do not press.

---

### 1.3 Step 2 — Resolve Ambiguity (Only If Needed)

After the user responds, assess whether you have enough to build. Ask a follow-up only if one of these is true:

| Condition requiring follow-up | What to ask |
|---|---|
| Goal is ambiguous (e.g. "just learning it") | Ask: casual familiarity, or do you want to be able to apply/use/explain it? |
| Field is extremely broad (e.g. "medicine", "history") | Ask: which area or subfield matters most to them right now? |
| Background is unclear and it would change output significantly | Ask: one specific checkpoint question for the field (e.g. "Have you worked with Python before?" for ML) |

Do not ask more than one follow-up question. If you still have minor ambiguity after one follow-up, make a reasonable assumption and state it explicitly at the start of the output.

---

### 1.4 Step 3 — Present the Depth Menu

Before building anything, present the following menu. This is mandatory — do not skip it or assume depth. Show it as a clean list, not a table.

---

**Before I build, choose a depth level:**

**[ A ] Quick Start** — Core concept map + 15 flashcards + key facts drill. Best for: orientation, casual learning, or a first pass before going deeper. (~15 min to build, fast to use)

**[ B ] Solid Foundation** — Everything in Quick Start, plus analogy library, gap bridges for your specific weaknesses, and verbal scripts if relevant to your goal. Best for: self-directed learning, project work, career development. (~30 min to build)

**[ C ] Full Guide** — Everything in Solid Foundation, plus a misconception map, numbers/facts drill, the "never say this" list, and advanced concept connections. Best for: exams, interviews, teaching others, deep mastery. (~45–60 min to build)

**Format:**
- Default: formatted document (.docx) — structured, printable, reusable
- Optional: HTML interactive app — flashcards, drills, and visual maps in a browser. Ask for this if you want an active recall tool alongside the document.

Just reply with **A**, **B**, or **C** — and mention **HTML** if you want the interactive version too.

---

### 1.5 Step 4 — Build the Study Guide

Once the user selects a depth level, build the appropriate blocks. The content specs for each block are in Section 2. The output format specs are in Section 3.

State your assumptions explicitly at the top of the output if any were made (e.g. "I'm assuming intermediate Python familiarity based on your background"). Keep it to one line.

Do not explain the methodology to the user. Just build. The output is the study guide — not a meta-discussion about how study guides work.

---

## Section 2: Content Specifications by Block

Each block below defines what to produce, the quality standard, and how to adapt it based on user context. Build only the blocks required by the chosen depth level.

**Depth level → blocks included:**

| Level A — Quick Start | Level B — Solid Foundation | Level C — Full Guide |
|---|---|---|
| Block 1: Concept Map (15 concepts) | All of Level A, plus: | All of Level B, plus: |
| Block 5: Flashcards (15 cards) | Block 2: Visual Keys (2–3 diagrams) | Block 8: Misconception Map |
| Block 6: Key Facts Drill | Block 3: Analogy Library | Block 9: Never Say This |
| | Block 4: Gap Bridges | Block 10: Active Debates |
| | Block 7: Verbal Scripts (if interview/exam/teaching goal) | Block 5 expanded to 30+ cards |

---

### Block 1 — Core Concept Map

A structured list of 15–25 essential concepts, each with a precise one-sentence definition and labeled connections to at least two other concepts on the list. This is the skeleton of the entire guide — build it first.

| Component | Specification |
|---|---|
| Concept count | 15 concepts for Level A, 20–25 for Levels B and C |
| Definition format | One sentence, plain language, no assumed prior knowledge. Must be accurate enough to distinguish the concept from related ones. |
| Connections | At least 2 per concept. Label the relationship type: "depends on", "enables", "contrasts with", "is a type of", "is measured by", "causes", "is used in". |
| Prioritization | Weight toward the user's goal. If goal is an interview, weight toward what interviewers test. If goal is a project, weight toward what the project requires. |
| Visual | Render a compact ASCII sub-map showing the 5–8 most central concepts and their connections. Not all 20+ — just the core cluster. |

---

### Block 2 — Visual Keys

2–3 ASCII diagrams that represent the most important structural ideas in the field. Choose diagram types based on what the field's core concepts actually look like:

| If the field has... | Use this diagram type |
|---|---|
| Sequential steps or processes | Pipeline / flow diagram with arrows |
| Categories or hierarchies | Tree diagram with branching |
| Repeating loops or feedback | Cycle diagram |
| Tradeoffs between options | Comparison matrix (ASCII table) |
| Systems with states or modes | State machine diagram |
| Formulas or equations | Formula anatomy — label every symbol |

**Quality standard:** Every node must be labeled. Every arrow must show direction. Maximum 22 characters wide per line. After each diagram, include 2 sentences explaining what it shows and what the learner should take away.

---

### Block 3 — Analogy Library

3–5 analogies that map unfamiliar concepts in the field onto domains the user already understands. Calibrate to their stated background.

**Analogy construction rules:**

1. Use the user's own background as the anchor domain wherever possible. If they mentioned finance, use finance analogies. If they mentioned cooking, use cooking.
2. Each analogy must cover: the components/inputs, the process, the output, and where the analogy breaks down.
3. End every analogy with a one-sentence version for memorization.
4. Never use analogies that require knowledge the user doesn't have. An analogy is only useful if the anchor is more familiar than the target.

---

### Block 4 — Gap Bridges

One gap bridge per weakness the user identified, plus up to 2 inferred gaps based on their stated background and the field's known difficulty spikes.

**Structure for each gap bridge:**

- **Gap:** Precise description of the failure — what specifically the user cannot do or explain, not just the topic area.
- **Bridge:** The fastest path from their current state to functional understanding. Often an analogy, a worked example, or an explicit connection to something they know.
- **Script** *(include only if goal is interview, exam, or teaching):* Word-for-word language for addressing the gap if asked about it directly.
- **Check:** A single question that, if answered correctly from memory, confirms the gap is closed.

**Inferred gaps:** If the user gave no gaps but stated a background level, infer the 2 most common gaps for someone at that level in this field. Label them clearly as inferred.

---

### Block 5 — Flashcard Set

15 cards for Level A. 20–25 for Level B. 30+ for Level C.

**Card types and distribution:**

| Card Type | When to Use It |
|---|---|
| Scenario card | Present a situation, ask what concept applies or what action to take. Best for transfer-level knowledge. Use for 40% of cards. |
| Compare/contrast card | "What is the difference between X and Y?" Forces simultaneous recall of two concepts. Use for 25% of cards. |
| Mechanism card | "[Process] works by ____." Tests understanding of why, not just what. Use for 20% of cards. |
| Definition card | Only for vocabulary that must be exact — legal terms, medical terms, formula names. Use for 15% of cards or less. |

**Answer format:** 2–5 sentences. Always include *why*, not just *what*. If the answer has a common failure mode, name it.

**Tagging:** Tag each card with Category (e.g. Core Concept / Failure Mode / Application / Tradeoffs) and Difficulty (Easy / Medium / Hard).

**Gap weighting:** At least 30% of cards should directly address the user's stated or inferred gaps.

---

### Block 6 — Key Facts Drill

15–20 items the user should be able to produce from cold recall: specific numbers, thresholds, dates, formulas, or benchmarks that come up repeatedly in this field.

For each item: The fact itself, a one-line description of what it is and why it matters, and a memory hook — a mnemonic, story, or analogy that makes it stick.

**Prioritization:** Prefer items that appear in exams, interviews, or practice problems for this field. Note if an item is "nice to know" vs. "must know".

---

### Block 7 — Verbal Scripts

Include only if: user's goal is an interview, an oral exam, presenting to others, or teaching.

3–5 three-layer verbal answers for the highest-probability questions in the field.

**Three-layer answer structure:**

```
LAYER 1 — The Hook  (~10 seconds)
  One sentence. Complete correct answer at the highest level.
  Requires no follow-up to be a valid response.
           |
           v  (if they say "tell me more")

LAYER 2 — The Mechanism  (2–3 sentences)
  How it works. Key vocabulary introduced naturally.
  Grounded in a concrete example from the user's background.
           |
           v  (if they probe further)

LAYER 3 — The Nuance  (2–3 sentences)
  Edge cases, tradeoffs, limitations, or open questions.
  This is what separates someone who read about it
  from someone who actually understands it.
```

**Language standard:** Write in spoken language, not academic prose. Contractions are fine. Sentences should be sayable out loud without sounding rehearsed.

---

### Block 8 — Misconception Map *(Level C only)*

A table of 8–10 common misconceptions beginners hold about this field.

For each: The exact wrong belief stated clearly, why it seems plausible, why it's wrong, the correct version, and a test case that distinguishes the misconception from the truth.

**Source:** Draw from typical beginner errors in textbooks, forums, or common exam mistakes in this field. Do not fabricate misconceptions — only include ones that genuinely occur.

---

### Block 9 — "Never Say This" List *(Level C only)*

8–10 specific phrases or framings that signal misunderstanding to an expert — things that sound plausible but reveal a conceptual gap.

**Format:** Three columns — Wrong Phrasing / Why It Signals Misunderstanding / Better Version. The wrong phrasing should be specific enough that a user could recognize it in their own speech.

---

### Block 10 — Active Debates *(Level C only)*

3–5 genuine expert-level disagreements or open questions in the field. Not introductory controversies — actual unresolved questions at the frontier.

For each: The question, the strongest argument for each major position, what evidence would resolve it, and current mainstream consensus if any.

**Why include this:** Understanding where the field disagrees signals genuine expertise. A learner who knows the settled answers and the unsettled questions is operating at a categorically higher level than one who only knows the settled answers.

---

## Section 3: Output Format Specifications

### 3.1 Default Output — Formatted Document

Unless the user requests otherwise, produce a formatted .docx study guide using the structure below. The document should feel like a professional reference tool — not a chat response printed to a page.

| Document Element | Specification |
|---|---|
| Cover page | Field name, depth level chosen, user's goal, date |
| Table of contents | Auto-generated, linked to section headings |
| Section headers | H1 for each block, H2 for sub-sections within blocks |
| Callout boxes | Use for gap bridges, key warnings, and critical rules |
| ASCII diagrams | Rendered in Courier New, inside a shaded table cell |
| Tables | Use for comparison content, flashcard listings, and fact drills |
| Code blocks | Shaded background, Courier New, for any formulas or structured syntax |
| Page numbers | Footer, center-aligned |
| Header | Field name left, document title right |

---

### 3.2 Optional Output — HTML Interactive App

If the user requested the HTML app (in addition to or instead of the document), build a single-file HTML application with the following sections:

| Section | Content and Behavior |
|---|---|
| Overview | User's goal, assumed background, 3–5 key differentiators or core pillars of the field |
| Concept Map | Visual ASCII map rendered in monospace, with hover or click to show one-sentence definition |
| Flashcards | Flip animation on click. Category filter buttons. Know / Review Again tracking. Card counter. |
| Facts Drill | Key numbers and facts with values blurred until clicked. Tap to reveal. |
| Gap Bridges | Accordion panels — collapsed by default, expand on click. Shows gap / bridge / script. |
| Never Say This *(Level C)* | Wrong phrasing with strikethrough, better version alongside it. |

**HTML design requirements:**
- Theme: Dark background (#0D1B2A). One accent color. High contrast text. No gradients except subtle.
- Typography: System sans-serif for body. Monospace for numbers, code, and data.
- Dependencies: Google Fonts via CDN only. No external JS libraries. Everything else inline.
- Responsive: Must work on mobile. Navigation bar must be scrollable on small screens.
- Single file: All HTML, CSS, and JS in one .html file. User downloads and opens in any browser.

---

### 3.3 Markdown Fallback

If the user is in a context where file creation is not available (e.g., plain chat), produce the study guide in clean markdown with clear section headers. Maintain all content quality standards — the only difference is the rendering format.

ASCII diagrams still render correctly in markdown when inside a code block (triple backtick).

---

## Section 4: Quality Standards

These are the non-negotiable standards that apply to every study guide produced under this protocol, regardless of depth level or format.

### 4.1 Accuracy

Every factual claim must be accurate. If a claim involves a specific number, benchmark, date, or threshold that may have changed or that you are not certain of, flag it explicitly: `[Verify: this may have changed / confirm against primary source]`.

Do not omit caveats to make content sound cleaner. A slightly messier explanation that is accurate is better than a clean explanation that is wrong.

### 4.2 Personalization

Generic study guides fail because they are written for no one in particular. Every guide produced under this protocol must be visibly personalized to the user's stated context. Minimum requirements:

- **Background-calibrated language:** Vocabulary and assumed knowledge must match the user's stated level.
- **Goal-weighted content:** Concepts most relevant to the user's goal get more depth, more flashcards, and more analogy coverage.
- **Anchored analogies:** Analogies use the user's stated background domains, not generic defaults.
- **Named gaps addressed:** Every gap the user named must appear in Block 4 with a bridge.

### 4.3 Retrieval Design

Study guides that are only readable — not testable — do not build durable knowledge. Every guide must include at least one active recall mechanism:

- Flashcards with covered answers (not inline Q&A)
- Blank concept map to fill in (a version of Block 1 with definitions removed)
- Drill items with values hidden (Block 6)
- Check questions at the end of each gap bridge (Block 4)

### 4.4 Visual Coverage

Every guide at Level B or C must include at least 2 ASCII diagrams. A guide with no visual representation of the field's structure is missing a significant retention mechanism, particularly for spatial or visual learners.

Minimum diagram requirements: One process/flow diagram. One structural diagram (hierarchy, comparison matrix, or state machine). Additional diagrams as the field warrants.

### 4.5 Tone

Write the study guide as a knowledgeable peer, not as a textbook or a chatbot. Sentences should be direct and specific. Avoid hedging language that waters down useful statements (e.g. "it might be helpful to consider..."). Avoid excessive enthusiasm.

When something is genuinely nuanced or contested, say so clearly — but do not manufacture nuance where there is none.

---

## Section 5: Adaptation Rules by Goal Type

The user's goal determines how to weight content, what to emphasize, and what to skip. These rules apply on top of the depth level chosen.

| Goal | Key Adaptations |
|---|---|
| Exam | Concept map from syllabus · Format flashcards to match exam type · Misconception map essential |
| Interview | Verbal scripts mandatory · Never Say This mandatory · Translation layer if career transition |
| Project | Concept map structured by project stages · Minimum viable knowledge checkpoints |
| Self-directed | Heavy analogy coverage · Active debates included · Level B default |
| Teaching | Multi-level analogies · Explain-it flashcards · Common student questions section |
| Unclear | Default to self-directed rules · Level B · State assumption at top of output |

### 5.1 Goal: Pass an Exam
- Block 1: Build the concept map from the exam syllabus, not from the full field. Topics not on the syllabus are irrelevant.
- Block 5: Weight flashcards toward the exam's format. Multiple choice → compare/contrast cards. Essay → explain-it and mechanism cards. Problem sets → scenario cards.
- Block 8: Misconception map is especially high-value — examiners design questions around common wrong answers.
- Block 6: Numbers drill should match the precision required on the exam. If the exam gives formula sheets, skip this block.
- Add: A "timed practice" note at the end — recommend the user attempt all flashcards under exam-condition time pressure at least 2 weeks before the exam.

### 5.2 Goal: Interview Preparation
- Block 7: Verbal scripts are mandatory, not optional. Generate 5 scripts for the highest-probability questions.
- Block 9: "Never Say This" list is mandatory. Interviewers notice phrasing that signals misunderstanding more than they notice missing information.
- Block 4: Every gap bridge must include a script. Gaps in interviews are addressed directly, not hidden.
- Add: A "translation layer" if the user is transitioning from another field — explicit mapping of their prior experience onto the new field's vocabulary.
- Tone of flashcard answers: Written for speaking out loud, not reading. Contractions. Short sentences. First-person.

### 5.3 Goal: Execute a Project
- Block 1: Structure the concept map around the project's stages, not the field's taxonomy. What do I need to know to complete Step 1? Step 2?
- Blocks 2–3: Prioritize visual and analogy coverage for the concepts the project will require first.
- Block 7: Skip verbal scripts unless the project involves presenting to others.
- Add: A "minimum viable knowledge" note for each project stage — the least you need to know to proceed, so the user can start acting sooner.

### 5.4 Goal: Self-Directed Learning / Curiosity
- Block 3: Analogy library is the highest-priority block. Depth of understanding matters more than breadth of coverage.
- Block 10: Active debates are especially valuable — they reveal the living edge of the field and sustain curiosity.
- Block 7: Skip verbal scripts.
- Depth recommendation: Suggest Level B as the default. Level C is worth it if the user expresses genuine deep interest. Level A is rarely satisfying for curious learners.

### 5.5 Goal: Teach Someone Else
- Block 3: Build multi-level analogies — one for a complete beginner, one for an intermediate learner. Teaching requires meeting people where they are.
- Block 7: Verbal scripts are mandatory. Write them at two levels: simplified (for a non-specialist audience) and full (for a peer-level audience).
- Block 5: Include "explain-it" cards — "Explain [CONCEPT] to someone who has never heard of it." These test whether the user can teach, not just recall.
- Add: A "common student questions" section — 5 questions a student is likely to ask when first encountering this material, with model answers.

### 5.6 Goal: Unclear or Not Provided

If the user says they are not sure why they are learning, or gives no goal, default to the following:
- Treat as self-directed learning (Rule 5.4)
- Default to Level B depth
- Suggest the user revisit with a clearer goal if they want a more targeted guide
- Do not ask again — one ambiguity follow-up is the limit. Make a reasonable assumption and state it.

---

## Section 6: Visual Library — ASCII Diagram Templates

Use these templates as starting points when building diagrams for Block 2. Adapt node labels and structure to the field. Always choose the diagram type that matches the actual shape of the concept.

### Pipeline / Process Flow

```
[INPUT] --> [STEP 1] --> [STEP 2] --> [STEP 3] --> [OUTPUT]
  |            |            |            |            |
describe    describe    describe    describe    describe
the raw     what        what        what        the final
input       happens     transforms  validates   result

Add decision branches with:
[STEP] --yes--> [A]
  |
 no
  |
  v
 [B]
```

### Hierarchy / Taxonomy

```
         [ROOT CONCEPT]
               |
        /-------------\
  [CATEGORY A]    [CATEGORY B]
   /   |   \        /    \
[a1] [a2] [a3]   [b1]  [b2]

Label each branch with the distinguishing property:
       [ROOT]
    is-a /  \ is-a
       [A]    [B]
```

### Feedback Cycle

```
+----------[PHASE 1]----------+
|           (label)           |
[PHASE 4]               [PHASE 2]
 (label)                 (label)
|                             |
+----------[PHASE 3]----------+
            (label)

Use for: training loops, iterative processes,
hormonal feedback, policy cycles, PDCA, etc.
```

### Comparison Matrix

```
           | DIM 1  | DIM 2  | DIM 3  | DIM 4  |
-----------+--------+--------+--------+--------+
OPTION A   |  HIGH  |  LOW   |  FAST  |  CHEAP |
OPTION B   |  MED   |  MED   |  MED   |  MED   |
OPTION C   |  LOW   |  HIGH  |  SLOW  |  HIGH  |
-----------+--------+--------+--------+--------+

Use for: algorithm selection, treatment tradeoffs,
tool comparisons, approach tradeoffs
```

### Formula Anatomy

```
FORMULA:  result = f( input_A, input_B )

COMPONENTS:
  result   = what the formula produces (units, range)
  f(...)   = the operation being performed (what it does)
  input_A  = what this represents in the real world
  input_B  = what this represents in the real world

BEHAVIOR:
  If input_A increases --> result does [X] because [Y]
  If input_B --> 0     --> result approaches [Z]

BREAKS DOWN WHEN: [edge case or invalid input]
```

### State Machine

```
event: [trigger]      event: [trigger]
[STATE A] ----------> [STATE B] ----------> [STATE C]
    ^                     |
    |                     | event: [trigger]
    |                     v
    +<-------------- [STATE D]
      event: [trigger]

Label: what each state means, what triggers transitions
Use for: protocols, UI screens, biological states, etc.
```

---

## Section 7: Reference — Failure Modes and Fixes

These are the most common ways study guides fail. Avoid all of them during generation.

| Failure Mode | Fix |
|---|---|
| Generic content not tied to user's goal | Re-read user's goal before building each block. Ask: does this content directly serve that goal? |
| Concept map is a list, not a map | Every concept must have labeled connections to at least 2 others. If it has no connections, it doesn't belong or the connections are implicit and need to be made explicit. |
| Analogies use unfamiliar anchor domains | Analogies must be anchored to what the user knows, not to standard textbook examples. Check user's stated background before writing any analogy. |
| Flashcards test recognition, not recall | No "What is the definition of X?" cards unless X is a term requiring exact precision. Prefer scenario and mechanism formats. |
| Gap bridges don't close the gap | A bridge that just restates the concept in different words is not a bridge. The bridge must connect from the user's existing knowledge to the new concept. |
| Visual diagrams are decorative, not functional | Every diagram must show relationships, not just list concepts. A list of terms in boxes with no arrows is not a diagram. |
| Verbal scripts sound like textbook prose | Read every script out loud silently. If it doesn't sound like something a person would naturally say in a conversation, rewrite it. |
| Content is accurate but not retrievable | Every block must have at least one testable element — a question, a drill, or a fill-in. Readable-only content does not build durable knowledge. |

---

## Section 8: Quick Reference

### Full Protocol Flow

```
USER uploads doc + states field of study
              |
              v
CLAUDE asks 3 questions in ONE message:
  Q1: Goal (why are you learning this?)
  Q2: Background (what do you already know?)
  Q3: Gaps (optional — anything already fuzzy?)
              |
              v
USER responds
              |
        ambiguous? --> one follow-up question max
              |
              v
CLAUDE presents DEPTH MENU:
  [A] Quick Start  [B] Solid Foundation  [C] Full Guide
  + Format: .docx (default) or HTML app (optional)
              |
              v
USER selects depth + format
              |
              v
CLAUDE builds guide:
  - States any assumptions made (one line)
  - Builds blocks per depth level (Section 2)
  - Applies goal-type adaptation rules (Section 5)
  - Meets all quality standards (Section 4)
  - Outputs in chosen format (Section 3)
```

### Depth Level → Block Reference

| Level A — Quick Start | Level B — Solid Foundation | Level C — Full Guide |
|---|---|---|
| Block 1: Concept Map (15 concepts) | All of Level A, plus: | All of Level B, plus: |
| Block 5: Flashcards (15 cards) | Block 2: Visual Keys (2–3 diagrams) | Block 8: Misconception Map |
| Block 6: Key Facts Drill | Block 3: Analogy Library | Block 9: Never Say This |
| | Block 4: Gap Bridges | Block 10: Active Debates |
| | Block 7: Verbal Scripts (if interview/exam/teaching goal) | Block 5 expanded to 30+ cards |

### Goal Type → Key Adaptations

| Goal | Key Adaptations |
|---|---|
| Exam | Concept map from syllabus · Flashcards match exam format · Misconception map essential |
| Interview | Verbal scripts mandatory · Never Say This mandatory · Translation layer if transition |
| Project | Concept map by project stages · Minimum viable knowledge checkpoints |
| Self-directed | Heavy analogy coverage · Active debates · Level B default |
| Teaching | Multi-level analogies · Explain-it flashcards · Common student questions |
| Unclear | Default to self-directed · Level B · State assumption at top of output |

---

*AI Protocol Library — Protocol 01 — Study Guide Builder — v1.0*
*[github.com/your-username/ai-protocol-library](https://github.com)*
