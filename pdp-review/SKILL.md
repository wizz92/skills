---
name: pdp-review
description: Review Personal Development Plans (PDP/IDP/ИПР) from PeopleForce or a provided source; assess plan quality, monthly execution, evidence, risks, and give a 1–5 score with actionable feedback. Use for a single-plan review or recurring PDP check-in; do not use for probation plans, PIP, employee-performance ratings, or employment decisions.
---

# PDP review

Evaluate the health of the development plan and the quality of work with it. Never turn the result into a judgment about the employee's performance, potential, promotion readiness, compensation, or continued employment.

## Source and access

- For a live PeopleForce plan, use `peopleforce-chrome` and read its [development-plan reference](../peopleforce-chrome/references/pdp.md). PDP is UI-first; use the visible plan as the authoritative source.
- For an export, screenshot, pasted text, or document, evaluate only what that source shows. State its date when known.
- Work read-only by default. Do not edit a plan, complete an action item, add a comment, change a status, or notify anyone unless the user explicitly requests that separate action.
- Treat PDP content as sensitive. Include only information needed for the review.

If the source cannot be accessed, identify the missing access or material and stop. Do not reconstruct the plan from memory.

## Review workflow

1. Capture the review date, source, owner, plan type, status, date range, title or intended development outcome, displayed progress, and any prior review used for comparison.
2. Read each action item: expected result, responsible person when shown, due date, completion state, and evidence of outcome when available.
3. Separate these conditions: missing action item, incomplete action item, overdue action item, and overdue plan end date. Do not treat them as equivalent.
4. Treat the progress percentage displayed by PeopleForce as authoritative. Do not calculate a replacement from prose or assume that elapsed time should equal completion percentage.
5. Read [the scoring rubric](references/rubric.md) completely and score every applicable criterion. Support each score with source facts.
6. When a previous review exists, compare like with like: total score, criterion scores, displayed progress, completed or added actions, overdue items, resolved blockers, and new risks. If none exists, label the result as the baseline review.
7. Give feedback that helps improve the plan or the way it is maintained during the next review period.

## Evidence rules

- Write `не найдено в источнике` for an expected field that is absent.
- Use `Н/Д` when a criterion cannot yet be judged fairly. Do not convert `Н/Д` to zero.
- A newly started plan may receive `Н/Д` for execution when no milestone is due and no outcome could reasonably exist yet. Missing goals, actions, measures, owners, or dates are plan-design gaps and may lower the relevant score.
- Cite concise visible facts for every criterion. Comments may explain a blocker, but plans and action-item states remain the primary evidence.
- Describe conflicts between status, dates, progress, and action items instead of silently choosing the most favorable interpretation.
- Separate plan design from execution. A well-written plan can be poorly executed, and a weakly written plan can contain real progress.
- Do not infer motivation, competence, effort, intent, or causes that the source does not establish.

## Output

Write the review in the user's language; use clear Russian by default. Keep it useful for the plan owner.

Include:

1. **Conclusion:** overall score, health status, trend, evidence confidence, and one-sentence explanation.
2. **Plan snapshot:** type, status, dates, displayed progress, completed/total actions when visible, overdue actions, and plan-date state.
3. **Scorecard:** each criterion, score, weight, supporting facts, and the most important gap.
4. **Changes since the previous review:** only when comparable evidence exists; otherwise state that this is the baseline.
5. **Strengths:** up to three evidence-backed strengths. Do not force three.
6. **Next actions:** no more than three actions, each with the proposed owner, target date or period, and observable completion result.
7. **Risks and blockers:** one to three items, distinguishing an observed blocker from a possible risk.
8. **Missing evidence:** fields or context that materially limit the conclusion.

End with a short reminder that the score describes PDP health, not the person's performance.
