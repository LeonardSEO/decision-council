# Scoring Rubric

## Designing decision criteria

Use 4–7 criteria. Weights must total exactly 100. Criteria should be:
- decision-relevant and specific to the user's objective
- distinct — avoid overlap
- measurable enough for comparative scoring
- explicit about time horizon and risk tolerance

**Example — software tool selection:**

| Criterion | Weight |
|---|---|
| Functional fit | 25 |
| Implementation effort | 15 |
| Reliability | 15 |
| Integration fit | 15 |
| Total cost | 15 |
| Maintainability | 10 |
| Strategic flexibility | 5 |
| **Total** | **100** |

Do not reuse these weights. Derive them from the specific decision.

---

## Scoring scale

Score each option 0–5 per criterion:

| Score | Meaning |
|---|---|
| 0 | Fails criterion or creates unacceptable harm |
| 1 | Very weak |
| 2 | Below requirements |
| 3 | Meets requirements |
| 4 | Strong |
| 5 | Clearly superior |

**Weighted score formula:**

```
sum( (criterion_score / 5) × criterion_weight )
```

Result is a score from 0 to 100.

---

## Evidence hierarchy

Prefer in this order:

1. Direct measurements, tests, supplied files, contracts, or primary records
2. Current official documentation and primary sources
3. High-quality independent research or comparative studies
4. Consistent expert consensus with known limitations
5. General knowledge and reasoning

Lower-ranked sources can still be useful. Confidence must reflect source quality.

---

## Bias controls

Apply during every review round:

- Anonymize authorship before review (Response A, B, C …)
- Vary or randomize response order where possible
- Apply the scoring rubric before reading candidate positions
- Score claims and outcomes — not length, presentation, or confidence tone
- Do not expose vote counts before the revision round
- Require a disconfirming signal from every advisor
- Preserve the strongest minority objection
- Run a counterfactual for the runner-up in High scrutiny mode

---

## Confidence calibration

| Range | Meaning |
|---|---|
| 90–100 | Direct, strong, current evidence points clearly to one option |
| 75–89 | Good evidence with minor gaps or one unresolved assumption |
| 60–74 | Reasonable case, but meaningful uncertainty remains |
| 45–59 | Genuine uncertainty — evidence splits or key facts are missing |
| 30–44 | Weak evidence base; assumptions are carrying the recommendation |
| 0–29 | Insufficient evidence; provisional only |

Do not use confidence to signal enthusiasm or rhetorical force. Use it to represent the actual strength of the evidence.

---

## Consensus thresholds

**Standard and High scrutiny (5 advisors):**

| Outcome | Condition |
|---|---|
| Strong consensus | ≥ 4/5 revised votes align + leading weighted score + no critical contradiction |
| Qualified consensus | ≥ 3/5 align + score lead ≥ 8 pts + one material caveat |
| No consensus | Neither threshold met, or critical contradiction could reverse outcome |

**Light (3 advisors):**

| Outcome | Condition |
|---|---|
| Strong consensus | 3/3 revised votes align + clear score lead |
| Qualified consensus | 2/3 align + clear score lead |
| No consensus | Split vote or contradicting evidence |

When there is no consensus, still provide one provisional recommendation if the user requested a decision. State clearly which assumption carries it.
