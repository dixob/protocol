# Protocol 04 — AI Discovery Sprint

> **Status:** ✅ Available
> **Audience:** Forward deployed engineers, AI consultants, and strategists scoping AI opportunities for a client or internal organization.
> **What makes this different:** Most AI discovery frameworks are strategic at the wrong level — too high to produce a buildable spec, too focused on technology to surface the real organizational constraints. This protocol is operational: it produces a prioritized roadmap and a PoC spec with defined success criteria, in under two weeks, from a standing start. It is built from direct consulting delivery across multiple enterprise client engagements.

---

## Part 1: User Guide

**When to load this protocol:**
Load it at the start of a discovery engagement — before your first stakeholder conversation. It will guide your fieldwork and then help you convert your findings into deliverables.

**What you bring:**
- Notes from stakeholder interviews (raw is fine — quotes, summaries, observations)
- Workflow observations or process documentation
- Any background context on the organization (industry, size, known constraints)

**What this protocol produces:**
1. **AI Opportunity Roadmap** — ranked use cases with effort/impact framing and sequencing rationale
2. **Priority PoC Spec** — a scoped, buildable definition of the first thing to build, with explicit success criteria and a go/no-go recommendation

**How to use it:**
Paste or upload your discovery notes into the same session as this protocol. The AI will synthesize your findings, run the prioritization framework, flag failure risks, and draft both deliverables. You review, correct, and finalize.

---

## Part 2: Operational Specification

*This section is written as a direct instruction set for an AI system. It is also fully readable by a human practitioner who wants to understand what the protocol is doing and why.*

---

### Section 1: Protocol Overview

#### 1.1 Trigger Conditions

This protocol activates when:
- This document is present in the conversation
- The user indicates they are scoping, assessing, or discovering AI opportunities for an organization
- The user has or is gathering fieldwork inputs (stakeholder interviews, workflow observations, or background context)

#### 1.2 What This Protocol Produces

Two deliverables, produced sequentially:

**Deliverable 1 — AI Opportunity Roadmap**
A prioritized list of 3–5 AI use cases, each with:
- Problem statement (1–2 sentences)
- AI-fit rationale (why AI, not simpler automation)
- Effort estimate (Low / Medium / High)
- Business impact estimate (Low / Medium / High)
- Feasibility flags (data, integration, org readiness risks)
- Recommended sequencing tier (Now / Next / Later)

**Deliverable 2 — Priority PoC Spec**
A buildable definition of the first use case to pursue, containing:
- Problem statement
- Business value (quantified where possible)
- Technical approach (model type, architecture sketch, data sources)
- Success criteria (specific, measurable, agreed by stakeholders)
- Evaluation rubric (how outputs will be scored)
- Known risks and mitigation notes
- Go / No-Go recommendation with conditions

#### 1.3 What This Protocol Does Not Cover

- Full technical architecture design or implementation planning
- Vendor or model selection beyond general category (e.g., "RAG-based retrieval" not "GPT-4o vs. Claude")
- Change management planning
- ROI modeling or business case construction
- Discovery for internal tooling without stakeholder access (use a different approach)

---

### Section 2: The Core Methodology

#### 2.1 Principle

Discovery fails in two directions: too slow (analysis paralysis, no recommendation) or too fast (builds start before scoping is done). This protocol enforces a two-week cadence that is fast enough to maintain stakeholder momentum and disciplined enough to prevent premature commitment.

The fundamental rule: **no PoC spec is produced until success criteria have been explicitly agreed with at least one decision-maker.**

#### 2.2 Sprint Structure

| Phase | Days | Activity | Output |
|---|---|---|---|
| 1 — Parallel Discovery | 1–3 | Stakeholder interviews + workflow mapping (run in parallel) | Raw notes, signals captured |
| 2 — Synthesis | 3–4 | Opportunity identification, AI-fit assessment, feasibility flags | Opportunity shortlist |
| 3 — Prioritization | 4–5 | Impact × feasibility scoring, first PoC selection | Ranked use cases |
| 4 — Validation | 5–7 | Technical check, stakeholder alignment, success criteria lock | Validated assumptions |
| 5 — Delivery | 7–10 | Roadmap + PoC Spec production, go/no-go framing | Final deliverables |

Days 7–10 include buffer for revision cycles. Most engagements close deliverables by Day 8 if Phase 4 is clean.

---

### Section 3: Phase 1 — Parallel Discovery (Days 1–3)

Run stakeholder interviews and workflow mapping simultaneously during this phase. Do not wait for interviews to complete before starting workflow observation.

#### 3.1 Stakeholder Interview Framework

**Target stakeholders (minimum):**
- One executive or decision-maker (budget authority, strategic framing)
- One operational lead (daily workflow ownership, pain point depth)
- One technical contact (data access, systems, integration constraints)

**Core questions for every stakeholder:**

| Question | What you're listening for |
|---|---|
| What takes the most time in your team's day-to-day? | High-volume, repetitive tasks — strongest AI candidates |
| Where do decisions get slowed down or reworked? | Bottlenecks with a pattern — automatable with right framing |
| What would success look like for your team six months from now? | Stakeholder's definition of value — use this in success criteria |
| What have you already tried? What didn't work? | Failure history — prevents re-running failed approaches |
| Who else needs to agree before something changes here? | Stakeholder map — surfaces hidden decision-makers |

**What to capture in your notes:**
- Direct quotes on pain points (verbatim where possible)
- Any existing tooling or automation attempts, including failed ones
- Mentions of data sources — what data exists, where it lives, who owns it
- Any resistance signals — people who may not want the workflow to change

#### 3.2 Workflow Mapping Guide

**Observe at least one workflow end-to-end.** Do not rely on stakeholder descriptions alone — people describe the ideal process, not the actual one.

**What to document:**
- Every manual step, decision point, and handoff
- Where humans are doing work that follows a consistent pattern (classification, extraction, summarization, formatting, routing)
- Where errors or rework commonly occur
- Approximate volume (how many times per day/week/month)
- Approximate time per instance

**Signal to prioritize:**
High-frequency + consistent pattern + currently manual = the strongest AI opportunity profile.

#### 3.3 Key Signals Across Both Activities

| Signal | What it means |
|---|---|
| "We spend a lot of time reading / reviewing / sorting [X]" | Candidate for classification or triage automation |
| "We copy information from one place to another" | Candidate for extraction or structured handoff |
| "We write the same type of thing over and over" | Candidate for drafting assistance or templated generation |
| "We have to check [source] before we can proceed" | Candidate for RAG-based retrieval |
| "It takes days to onboard someone to this" | Candidate for documentation or knowledge retrieval tooling |
| "We're not sure if [X] is right until we review it" | Candidate for eval-gated AI with human-in-the-loop |

---

### Section 4: Phase 2 — Synthesis (Days 3–4)

#### 4.1 Opportunity Identification

From your discovery notes, extract every distinct problem that could plausibly benefit from AI. Do not filter yet. Aim for 8–15 candidate opportunities.

For each candidate, capture:
- Problem statement (one sentence)
- Affected workflow (which process, what step)
- Evidence from discovery (quote or observation that surfaced this)
- Preliminary AI-fit assessment (see 4.2)

#### 4.2 AI-Fit Assessment

Before scoring, apply this filter. For each candidate, ask: **Is AI actually the right tool here?**

| If the problem is... | Consider instead |
|---|---|
| High-frequency, rule-based, fully deterministic | Simple automation or RPA (not LLM) |
| A data pipeline or ETL problem | Structured data tooling, not AI |
| An organizational coordination problem | Process redesign, not technology |
| A quality problem caused by unclear requirements | Requirements work, not AI |

**AI is the right fit when:** The task involves language, judgment, pattern recognition across unstructured data, or context-dependent output where the "right answer" varies and cannot be reduced to a rule.

Flag any candidate where a simpler solution would work. Include this in the roadmap — it demonstrates analytical rigor and builds stakeholder trust.

#### 4.3 Feasibility Flags

For every candidate that survives the AI-fit filter, check these:

| Risk dimension | What to assess |
|---|---|
| **Data access** | Does the relevant data exist? Is it accessible to an AI system? Who owns it? Any compliance/privacy constraints? |
| **Integration** | What systems need to connect? Are APIs available? What's the latency tolerance? |
| **Output sensitivity** | If the AI is wrong, what's the consequence? Does this require human review? |
| **Org readiness** | Who will own this after it's built? Is there a clear maintenance path? Will the affected team adopt it? |

Mark each candidate as: ✅ No flags / ⚠️ Flags — manageable / 🚫 Blocked — needs resolution before proceeding.

---

### Section 5: Phase 3 — Prioritization (Days 4–5)

#### 5.1 Scoring Framework

Score each surviving candidate on three dimensions (1–3 scale):

| Dimension | 1 | 2 | 3 |
|---|---|---|---|
| **Business Impact** | Marginal improvement | Meaningful efficiency or quality gain | Significant cost, revenue, or risk impact |
| **Technical Feasibility** | Major unknowns, blocked flags | Manageable complexity, no blockers | Clear path, data accessible, low integration risk |
| **Speed to Value** | Months to first usable output | Weeks to functional prototype | Days to validated PoC |

Calculate a total score (max 9). Adjust for organizational context — a high-impact item with a ⚠️ flag is worth discussing; a 🚫 blocked item does not go on the roadmap until the blocker is resolved.

#### 5.2 Roadmap Tiers

Assign each use case to a tier:

- **Now (Tier 1):** Score 7–9, no blocking flags. The first PoC comes from here.
- **Next (Tier 2):** Score 5–6, or 7+ with manageable flags. Build after Tier 1 is validated.
- **Later (Tier 3):** Score <5, or has unresolved flags. Keep on radar; do not commit.

#### 5.3 Selecting the First PoC

From Tier 1, select the use case that best satisfies:
1. Stakeholders can define "success" in observable, measurable terms
2. A functional prototype is achievable in 1–2 weeks
3. At least one decision-maker has stated this is a priority

If multiple candidates meet these criteria, prefer the one with the narrowest scope — a fast, clean win over a larger, riskier build.

---

### Section 6: Phase 4 — Validation (Days 5–7)

This phase exists to prevent the two most expensive discovery failures: committing to a PoC before success criteria are defined, and discovering a technical blocker after the PoC has started.

#### 6.1 Technical Validation Checklist

Before writing the PoC spec, confirm all of the following:

- [ ] Relevant data exists and is accessible to the system you plan to build
- [ ] Required APIs or integrations are available and have been tested or documented
- [ ] Latency and reliability requirements are defined and achievable
- [ ] A human-review layer has been scoped if output sensitivity requires it
- [ ] There is a clear owner for post-PoC maintenance

If any item is unconfirmed, resolve it before writing the spec — not after.

#### 6.2 Stakeholder Alignment Checkpoint

Before finalizing the PoC spec, conduct a brief alignment session with the key decision-maker:

- Share the shortlisted use cases and your recommended first PoC
- Present the proposed success criteria — get explicit agreement, not just acknowledgment
- Surface any concerns or constraints not captured in Phase 1

**The success criteria must be agreed here.** If the stakeholder cannot state what a successful outcome looks like in concrete terms, the PoC spec cannot be written. Surface this as a risk and work to resolve it before proceeding.

---

### Section 7: Phase 5 — Deliverables (Days 7–10)

#### 7.1 AI Opportunity Roadmap — Format

Produce a structured document containing:

**Header:** Organization name, engagement date, sprint conductor, document version

**Executive Summary (3–5 sentences):**
Key findings from discovery. Overall AI readiness assessment. Recommended starting point and rationale.

**Use Case Inventory:**
For each Tier 1–2 use case, one block containing:
- Use Case Name
- Problem Statement
- AI-Fit Rationale
- Impact / Feasibility / Speed scores
- Feasibility Flags (if any)
- Tier assignment and sequencing note

**Use cases where simpler alternatives are recommended:**
List any candidates where AI is not the right fit, with the recommended alternative. This section builds credibility.

**Roadmap Summary Table:**
| Use Case | Tier | Impact | Feasibility | Recommended Next Step |

#### 7.2 Priority PoC Spec — Format

Produce a separate, standalone document containing:

**Problem Statement**
What problem are we solving? For whom? What is the current cost (time, money, quality, risk) of not solving it?

**Proposed Solution**
What will the AI do? What type of model or architecture (e.g., "LLM-based classification," "RAG retrieval over internal documents," "structured extraction pipeline")? What does the human-in-the-loop layer look like, if any?

**Data and Integration Requirements**
What data does this require? Where does it live? What systems need to connect? What has been confirmed vs. assumed?

**Success Criteria**
*These must be agreed with the decision-maker before this spec is finalized.*
- Primary metric: [specific, measurable outcome]
- Secondary metric: [supporting signal]
- Minimum acceptable threshold: [the floor below which the PoC does not proceed to production]

**Evaluation Rubric**
How will outputs be scored? Who reviews them? What does a passing output look like vs. a failing one?

**Known Risks and Mitigations**
What could go wrong? What has already been flagged? What is the mitigation plan?

**Go / No-Go Recommendation**
Based on current information: Go / No-Go / Conditional Go (with stated conditions).

---

### Section 8: Failure Mode Reference

These are the six most common ways an AI discovery sprint fails. Each has a documented prevention step built into this protocol.

---

**Failure Mode 1: Premature PoC Commitment**

*What happens:* A stakeholder sees an impressive AI demo during discovery and commits to building before the use case is scoped. The team starts building against an undefined target.

*Why it's damaging:* Success criteria get defined retroactively, often by whoever is most vocal at review time. The PoC "succeeds" by one measure and "fails" by another, and no one agrees which measure was supposed to matter.

*Prevention:* Section 6.2 — Success criteria are locked with the decision-maker before the PoC spec is written. No spec without agreed criteria.

---

**Failure Mode 2: Data Availability Assumptions**

*What happens:* A use case looks strong through Phase 2 and 3. In Phase 5, you discover the relevant data is siloed, owned by a different team, subject to compliance restrictions, or not actually in the format assumed.

*Why it's damaging:* Discovery time is wasted. Worse, if the PoC starts before this is discovered, it fails for a non-technical reason that could have been caught in week one.

*Prevention:* Section 6.1 — Technical validation checklist must be completed before the PoC spec is written. Data access is the first item on that checklist.

---

**Failure Mode 3: Success Criteria Drift**

*What happens:* Different stakeholders have different definitions of success that were never surfaced or reconciled. Finance wants cost reduction. Operations wants less manual work. Engineering wants clean integration. The PoC is reviewed against all three simultaneously and meets none of them cleanly.

*Why it's damaging:* A PoC that should advance to production gets blocked by unresolved disagreement that wasn't a technical problem.

*Prevention:* Section 6.2 — The alignment checkpoint explicitly requires agreement on success criteria from the decision-maker, not just acknowledgment from the room.

---

**Failure Mode 4: Org Readiness Blind Spot**

*What happens:* The technical solution is sound and the PoC succeeds. There is no clear owner for production deployment, no budget for maintenance, and the team that would use it wasn't involved in the discovery.

*Why it's damaging:* Working PoCs die in staging. The engagement closes as a success and the work never gets used.

*Prevention:* Section 6.1 checklist item — "There is a clear owner for post-PoC maintenance." Section 4.3 feasibility flag — org readiness is assessed for every candidate.

---

**Failure Mode 5: Solutioning Before Problem Definition**

*What happens:* The client arrives at discovery having already decided they want to "use AI" or "build something with LLMs." The discovery gets co-opted — stakeholder interviews become requirements sessions for a solution that was never validated.

*Why it's damaging:* The real high-value problems don't get surfaced. You build what the client asked for, not what they needed.

*Prevention:* Section 3.1 interview questions are problem-first, not solution-first. Section 4.2 AI-fit assessment requires justification for every use case — the answer can be "simpler solution recommended."

---

**Failure Mode 6: Integration Complexity Underestimation**

*What happens:* The AI component works. Connecting it to the organization's actual systems — their CRM, their document store, their internal APIs — takes three times as long as the model work.

*Why it's damaging:* PoC timelines slip. Stakeholders lose confidence. The AI capability is technically proven but practically undeliverable.

*Prevention:* Section 6.1 checklist — required APIs and integrations must be confirmed available and documented before the spec is written. Integration complexity is factored into the feasibility score in Section 5.1.

---

### Section 9: AI Execution Instructions

*Instructions for the AI model when this protocol is active in a session.*

When a user uploads this protocol and provides discovery inputs (notes, interviews, observations), execute the following:

**Step 1 — Assess what you have.** Identify which phases have been completed. Note any gaps (e.g., missing technical contact interview, no workflow observation data).

**Step 2 — Surface gaps before synthesizing.** If critical inputs are missing — especially technical validation data or any stakeholder's definition of success — flag this explicitly before producing deliverables. Do not produce a PoC spec if success criteria are absent.

**Step 3 — Run Phases 2–4 against the provided notes.** Extract candidate opportunities, apply the AI-fit filter, flag feasibility risks, score and rank use cases. Show your reasoning for prioritization decisions — the user may have context that changes the scoring.

**Step 4 — Draft deliverables in the formats specified in Section 7.** Label assumptions clearly. Where the user's notes are thin on a required field, flag it as "[CONFIRM WITH STAKEHOLDER]" rather than inventing content.

**Step 5 — Flag any active failure mode risks.** If the inputs suggest a failure mode from Section 8 is present or likely, surface it explicitly before the deliverables section.

**Output format:** Produce the Roadmap first, then the PoC Spec as a separate block. Use the section headers from 7.1 and 7.2 exactly — these documents may be shared with client stakeholders.

---

*Protocol 04 — AI Discovery Sprint · AI Protocol Library · Built from direct consulting delivery across enterprise AI engagements.*
