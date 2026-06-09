---
name: decision-council
description: Use when a user needs a consequential choice, verdict, recommendation, second opinion, or pressure test where multiple criteria or perspectives matter. Use for vendor selection, strategy, hiring, investment, architecture, policy, or any question where a poor decision has material cost. Do not use for factual lookups, simple calculations, rewriting, or low-stakes questions with one obvious answer.
---

# Decision Council

Produce one defensible collective recommendation by combining independent expert perspectives, adversarial review, revision, and evidence-weighted synthesis. Optimize for decision quality — not harmony, not novelty, not confident-sounding prose.

## Choose depth automatically

| Depth | When | Agents |
|---|---|---|
| **Light** | Low-stakes, reversible, simple | 3 advisors → direct synthesis |
| **Standard** | Normal business or personal decision | 5 advisors → review → revision → synthesis |
| **High scrutiny** | Costly, hard to reverse, legal, medical, financial, security, or strategic | Research + 5 advisors → review → revision → counterfactual → synthesis |

Do not ask the user to choose a depth. Infer it from the stakes and reversibility.

## Step 1 — Decision brief

Before convening the council, establish:
- exact decision and alternatives
- user's objective and hard constraints
- 4–7 decision criteria with weights totaling 100
- time horizon and reversibility
- known facts, assumptions, and unknowns that could change the outcome

Ask **one** clarification question only when a missing fact could realistically reverse the recommendation and cannot be responsibly assumed. Otherwise state the assumption and continue.

## Step 2 — Evidence packet

Create one neutral evidence packet shared by every advisor. Separate:
- **Verified facts** — from supplied files, calculations, tests, authoritative sources
- **Inferences** — conclusions reasonably derived from facts
- **Assumptions** — necessary but unverified premises
- **Unknowns** — missing information that creates decision risk

For High scrutiny: use tools, retrieval, or web research before deliberation. Once independent analysis begins, new evidence may only enter by reopening this step.

## Step 3 — Council

See `references/personas.md` for full persona instructions.

**Five voting advisors:**
1. **Domain Specialist** — dynamically chosen for the subject (e.g. software architect, financial analyst, automotive expert)
2. **Contextual Specialist** — fills the most critical uncovered dimension (e.g. customer advocate, security specialist, compliance expert)
3. **Evidence Auditor** — tests source quality, logic, assumptions, and uncertainty
4. **Red Team Analyst** — searches for failure modes, hidden costs, lock-in, and disconfirming evidence
5. **Execution Pragmatist** — evaluates feasibility, resources, dependencies, reversibility

**Non-voting:**
- **Problem Framer** — defines the right decision before the council convenes
- **Chair** — aggregates, does not vote, cannot override without citing a specific factual or logical error

For Light: use Domain Specialist, Red Team Analyst, Execution Pragmatist.

Use isolated subagents when available. Give every advisor the same decision brief and evidence packet. Do not expose other advisors' positions during the independent round.

## Step 4 — Independent memos

Each advisor returns this exact structure:

```
RECOMMENDATION: <one option or verdict>
CONFIDENCE: <0–100>
DECISIVE REASONS:
- <reason>
- <reason>
- <reason>
CRITICAL ASSUMPTION: <assumption that carries the recommendation>
BIGGEST RISK: <most likely failure mode>
STRONGEST EVIDENCE AGAINST MY POSITION: <fact or argument>
WHAT WOULD CHANGE MY RECOMMENDATION: <specific disconfirming signal>
```

Take the assigned perspective seriously. Do not force disagreement or ignore relevant counterevidence. Do not expose private chain-of-thought.

## Step 5 — Blind peer review (Standard + High scrutiny)

- Anonymize memos as Response A, B, C … — keep persona identities hidden
- Vary presentation order when possible
- Evaluate substance, not writing style, length, or confidence tone

See `references/scoring-rubric.md` for the full scoring method.

Each reviewer returns:
```
STRONGEST SUPPORTED CLAIM:
WEAKEST OR UNSUPPORTED CLAIM:
OVERLOOKED TRADE-OFF:
EVIDENCE CONTRADICTION:
BEST ALTERNATIVE UNDER THE CRITERIA: <option + reason>
```

Score every alternative 0–5 on each criterion. Apply weights → score out of 100.

## Step 6 — Revision

Return peer-review findings to each original advisor (without vote counts or identities).

Each advisor submits:
```
REVISED RECOMMENDATION:
REVISED CONFIDENCE: <0–100>
POSITION CHANGED: yes / no
REASON FOR CHANGE: <evidence or argument — not social pressure>
STRONGEST REMAINING OBJECTION:
```

An advisor must not change position merely because it appears to be in the minority.

## Step 7 — Aggregation

The Chair calculates:
- revised vote count per alternative
- median confidence for the leading recommendation
- weighted criterion scores (see `references/scoring-rubric.md`)
- score margin between first and second place
- unresolved factual contradictions
- strongest minority objection

Classify outcome:

| Outcome | Threshold |
|---|---|
| **Strong consensus** | ≥ 4/5 revised votes align + highest weighted score + no critical contradiction |
| **Qualified consensus** | ≥ 3/5 align + score lead ≥ 8 pts + one material caveat |
| **No consensus** | Neither threshold met, or critical contradiction remains |

Light thresholds: 3/3 for strong, 2/3 with clear score lead for qualified.

When there is no consensus, still give one provisional recommendation if the user requested a decision. State the assumption it depends on. Never refuse to recommend when asked.

The Chair may depart from the vote or weighted score only by identifying a specific factual error, logical error, or violated hard constraint.

## Step 8 — Final integrity check

Before answering, verify:
- every stated fact is supported
- recommendation matches the user's objective and constraints
- the result was not driven by response order, length, or confidence tone
- the strongest case for the runner-up was considered
- a material minority objection is preserved
- confidence reflects evidence quality
- the answer contains **one** clear recommendation

For High scrutiny: identify the single most plausible change in facts, assumptions, or criterion weights that would make the runner-up win.

## Output

Use `assets/final-answer-template.md`.

**Default:** show decision and synthesis only — not full persona transcripts.
Show complete council record only when the user explicitly asks for it.
Create an HTML report or file artifact only when the user explicitly requests one.

## Failure handling

- Evidence insufficient → give provisional decision, identify the decisive missing fact
- Retrieval fails → state which claims could not be verified
- Persona produces unsupported claims → exclude from scoring, flag it
- Chair disagrees with council → may override only with a named factual or logical error, stated transparently
