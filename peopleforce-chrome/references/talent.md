# Recruiting, performance, and surveys

Use this reference for recruiting, candidates, 1:1, goals, KPI, reviews, feedback, and surveys. For PDP / development plans, read [pdp.md](pdp.md) instead.

The sidebar expands `Рекрутинг` to vacancies, candidates, hiring plan, tests, and interviews; `Эффективность` to 1:1, goals, feedback, KPI, reviews, and development plans; `Опросы` to engagement and lifecycle.

## Recruiting

- Vacancies: `/recruitment/vacancies`
- Candidates: `/recruitment/applicants`
- New candidate: `/recruitment/applicants/new`
- Hiring plan / vacancy requests: `/recruitment/vacancy_requests`
- Tests: `/recruitment/tests`
- Interviews: `/recruitment/interviews`

Tenant controls observed: vacancies use `Поиск`, `Добавить фильтр`, `Настройки вида`, and `Экспортировать в`; candidates add `Кандидат` and show columns for name, score, applications, added date, last contact, and recruiting-data consent; hiring requests expose ID, planned date, creator, created date, and status. Tests show title, status, participants, and average score.

The global `Быстрое добавление` menu contains `Кандидат`, but use `/recruitment/applicants/new` when creation is explicitly requested. Before changing a candidate stage, rejecting a candidate, sending email, scheduling an interview, or creating an offer, verify candidate identity and vacancy, inspect the current state, and follow browser confirmation requirements. Do not make the hiring decision for the user.

Search/filter before opening a candidate or vacancy. On a vacancy, treat the pipeline board and stage counts as the authoritative visual state; scope actions to the correct application card. A name alone is insufficient: use email, phone, candidate ID, source, and current vacancy/application. A candidate can have multiple applications, so a stage action must target the verified application.

Creating a candidate requires deduplication and explicit consent/source handling. Hiring-plan approvals, interviews, tests, email, offers, rejection, and deletion are representational or consequential. Inspect recipients, time zone, vacancy, template/content, attachments, stage automations, and notifications immediately before submission.

## Performance

- 1:1 list: `/performance/one_on_ones/company`
- New 1:1: `/performance/one_on_ones/new`
- Goals: `/performance/objectives/company`
- Feedback: `/performance/feedbacks/company`
- New feedback: `/performance/feedbacks/new`
- KPI: `/performance/key_performance_indicators/company`
- Review cycles: `/performance/review_cycles/company`
- Development plans: `/performance/development_plans/company`

The shorter routes currently redirect to these `/company` views. Observed controls: all lists support search or filtering; 1:1 exposes organizer and previous/next meeting; KPI is a month grid by name/owner/type; development plans show person, type, status, dates, and progress.

The left menu groups these under `Эффективность`. The global `Быстрое добавление` menu also exposes `1:1` and `Фидбек`.

For 1:1, verify both participants, owner, date/time/timezone, recurrence, talking points, visibility, and notifications. For feedback, verify recipient, author visibility/anonymity, wording, and whether it is requested or unsolicited. Do not save or send during exploration.

For goals and KPI, filter by cycle/status/owner/team/date before reading. Distinguish owner from contributors and current progress from target. Creating a KPI result or changing goal progress writes a performance record; preserve user-supplied value, unit, and period exactly.

For review work, identify the cycle, employee, evaluator, and stage before reading or entering content. Never infer ratings, promotion, pay, or employment decisions. When asked to summarize, separate employee self-assessment, manager assessment, and system status. When asked to enter user-provided feedback or scores, preserve the wording and numbers exactly unless the user requests editing.

Do not open every review in a cycle. Filter to person/evaluator and inspect only the needed response section. A score may be calculated, hidden, incomplete, calibrated, or final; retain its visible label and stage. Launching, closing, reopening, publishing, reminding, calibrating, and submitting are consequential.

## Surveys

- Engagement surveys: `/pulse/company/surveys`
- Lifecycle survey participants: `/pulse/lifecycle/participants`
- Quick poll creation: `/polls/new`

Engagement surveys expose `Создать опрос`; lifecycle participants expose `Поиск`, `Добавить фильтр`, `Настройки вида`, and columns for person/form, sent date, and status.

Creating, launching, publishing, closing, or messaging survey participants is an external side effect. Inspect configuration first and confirm at the final action when required.

Before reading results, verify survey type, status, dates, population, response count, anonymity, filters, and minimum-cohort rules. Do not combine small cohorts or cross-reference anonymous answers with identity data. Dashboard charts are UI-authoritative; structured authorized response analysis is often better through v4 API.

## Relevant reports

- 1:1 status: `/reports/perform/one_on_ones`
- Goal ownership and status: `/reports/perform/ownership`
- Company KPI: `/reports/perform/key_performance_indicators`
- Development plans: `/reports/perform/development_plans`
- Vacancy pipeline funnel: `/reports/recruit/pipeline_funnel`
- Hiring pipeline statistics: `/reports/recruit/pipeline_statistics`
- Candidate sources: `/reports/recruit/candidate_sources`
- Vacancy funnel: `/reports/recruit/vacancy_funnel`
- Time to hire: `/reports/recruit/time_to_hire`
- Time to fill: `/reports/recruit/time_to_fill`
- Time to disqualify: `/reports/recruit/time_to_disqualify`
- Time in stage: `/reports/recruit/time_in_stage`
- Recruiter activities: `/reports/recruit/activities`

Open the most specific report directly, set only the requested filters, and use the page's authoritative totals or export result. Do not traverse the full report catalog unless the requested report is unclear.
