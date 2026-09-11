# PDP / development plans

Use this reference for Personal Development Plans (PDP), Individual Development Plans (IDP/ИПР), Performance Improvement Plans (PIP), career plans, and any PeopleForce request phrased as `План развития`. In this tenant, these are one feature with a selectable plan type; never infer which type a person should receive.

## Choose the right surface

PDP is UI-first. The Company API does not expose a complete development-plan workflow. Use Chrome for lists, templates, plan content, action items, progress, comments, completion, permissions, and the official report.

A hybrid is useful only when an API lookup cheaply resolves an employee ID or validates a large target population. Return to the UI for every PDP read or change and verify the same person there. Do not claim that API employee or task records are PDP records.

## Direct routes and views

- Company plans: `/performance/development_plans/company`
- Team plans: `/performance/development_plans/team`
- My plans: `/performance/development_plans/my`
- Official development-plan report: `/reports/perform/development_plans`
- Types and templates: `/settings/performance/development_plan_types`

The main list has `Компания`, `Команда`, and `Мои` views. It supports `Поиск` and `Фильтр`; the observed filters are `Тип` and `Статус`. Read the matching row only. The useful columns are person/owner, type, status, start date, end date, and progress.

Use the report for portfolio questions such as all active plans, expiring plans, plan coverage, or progress across people. Its table exposes employee, type, start date, end date, progress, and status; set the requested date range before reading or exporting. Do not walk every employee profile when this report answers the question.

For one employee, the profile's performance area is usually the clearest view. Plans there are grouped into active/open and completed. Verify the employee with at least one additional attribute before opening a plan; for creation or completion, use two identity attributes.

## Create a plan

`Новый план` offers two paths:

- `Использовать шаблон`: opens the template library. Review the template, included action items, and any per-item due dates before choosing it. The library can expose `Задать срок выполнения` for action items.
- `Создать с нуля`: opens the plan form directly.

Use these UI actions rather than navigating directly to the internal `/new` URLs: the tenant loads the flow through Turbo panels and a direct navigation may be blocked by the browser client.

The tenant's initial form from the company list currently posts to `/performance/development_plans` and exposes:

- `Владелец`
- `Тип плана развития`
- `Диапазон дат`

The employee-profile flow may also expose an editable plan title. The documented default period starts today and ends 12 months later, but read the actual displayed dates; never assume the default is acceptable. A template uses the same final form with the selected template attached.

Before pressing `Создать`, verify the exact owner/employee, type, date range, selected template, imported action items, and any due dates. Creating the plan is a consequential HR write and may expose development or performance information to other roles, so follow action-time confirmation requirements.

After creation, verify and, only when requested, edit the plan title and content in the plan editor. Plans can contain action items added from the editor toolbar or slash command. Editing may autosave: do not type exploratory text, draft judgments, or unapproved wording into a live plan.

## Read and audit a plan

For a single plan, capture only:

1. employee/owner and plan type;
2. current status and date range;
3. title or stated development outcome;
4. action items, assignees if shown, due dates, and completion state;
5. displayed progress;
6. comments or approval context only when the request needs them.

Progress is derived from completed action items. Treat the displayed percentage as authoritative; do not estimate it from prose. Separate overdue action items from an overdue plan date, and separate missing action items from incomplete ones.

For a portfolio audit, filter the official report first, then open only anomalous plans: expired dates, low or zero progress, missing actionable content, or a status/date mismatch. Report facts and gaps; do not rank people or infer performance, readiness, promotion, termination, or compensation decisions.

## Edit actions and progress

Action items are operational records inside the plan. Before adding or changing one, verify the exact plan, action text, responsible person if applicable, due date, and current completion state. Preserve user-provided wording and dates exactly unless editing was requested.

The plan's action-items view supports active items, search, and showing completed items. Completion changes progress and may affect manager interpretation. Never mark an item complete merely because its due date passed or a similar task is complete elsewhere.

Comments and shared links can reveal sensitive performance context. Read or copy them only when necessary. A manager may be able to comment or edit depending on role permissions; visible UI controls, not job-title assumptions, are authoritative.

## Complete or reopen a plan

Completion is performed from the plan's three-dot menu with `Завершить`; the plan then moves to the completed group. This is a consequential status change. Verify that all intended action items and dates are final, state the current and target status, and confirm at the final action when required. Do not complete a plan just because progress shows 100%, and do not reopen one unless the user explicitly requests it and the UI offers that action.

After completion, verify the new status and presence in the completed view. If the state did not change, report the visible error or permission issue rather than retrying the action blindly.

## Types, templates, feature access, and permissions

Types and templates live at `/settings/performance/development_plan_types`. Standard concepts may include IDP, PDP, PIP, and career plans; the tenant can also have custom types. A type organizes templates. Creating, renaming, moving, or deleting a type/template affects organization-wide authoring, so inspect dependencies and confirm the exact change.

If development plans are absent, check whether Perform development plans are enabled in general Perform settings, then check role permissions. By default behavior documented by PeopleForce, employees can work with their own plans and managers/team leads may edit plans for employees in their scope, but tenant role configuration can override this. Never bypass or broaden permissions.

## Fast locator cues

- New-plan menu: `[data-cy='employee_development_plans_add_actions']`
- Use template: `[data-cy='employee_development_plans_add_using_template_action']`
- Create from scratch: `[data-cy='employee_development_plans_add_from_scratch_action']`
- Choose a displayed template: scope `[data-cy='employee_development_plans_add_action']` to the verified template card
- List/report filter: `[data-cy='development_plan_filters_action']` when present

Prefer labels and exact visible text when they are stable. Never choose a repeated template or action by index; scope to its named card or plan.

## Minimal verification output

For reads, report the selected view/report and only the requested fields. For changes, report the employee/plan, exact delta, visible success or resulting state, and any notification, permission, or ambiguity still unresolved. Avoid reproducing full plan prose or other employees' data unless the user needs it.
