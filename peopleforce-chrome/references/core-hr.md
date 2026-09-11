# Core HR and employee lifecycle

Use this reference for employee lookup, profile fields, teams/org chart, absence/calendar, onboarding, probation, and offboarding. Documents, assets, notes, and profile tasks are covered in [operations.md](operations.md).

The `Сотрудники` menu expands to `/people`, `/teams`, and `/people/chart?view=chart`.

## Employee directory

- Directory: `https://qwertysoftware.peopleforce.io/people/list` (`/people` redirects here)
- New hire form: `/people/new`
- Directory controls observed: searchbox `Поиск`, button `Добавить фильтр`, button `Настройки вида`, button `Экспортировать в`.
- The default directory includes a status filter such as `Работающие` and a paginated table. Search first; do not page through all employees.
- Useful visible identity columns: full name, position, department, location, manager, start date.

To locate a person, use the user-provided exact name, email, or employee number where supported, wait for filtering to settle, and inspect only matching rows. Confirm identity with one additional attribute for a read and two for a consequential write. Preserve the numeric employee ID from the verified profile URL for direct navigation during the task.

Use `Добавить фильтр` for status, department, location, manager, hire/termination date, or another available field instead of paging. `Настройки вида` can persist presentation for the user; inspect it only when the requested field is not visible and do not save layout changes unless requested. Before export, verify filters, columns, format, and sensitive scope.

## Profile route patterns

Replace `:id` with a verified employee ID.

- Personal: `/people/:id`
- Work: `/people/:id/job`
- Compensation: `/people/:id/compensations`
- Absence: `/people/:id/leave`
- Performance summary: `/people/:id/performance`
- Documents: `/people/:id/documents`
- Tasks: `/people/:id/tasks`
- Workflows: `/people/:id/workflows`
- Assigned assets: `/people/:id/asset_assignments`
- Emergency contacts: `/people/:id/emergency_contacts`
- Dependents: `/people/:id/dependents`
- Notes: `/people/:id/notes`

The profile header exposes `Личное`, `Работа`, `Компенсация`, `Отсутствия`, `Эффективность`, `Документы`, and `Больше`. `Больше` expands to tasks, workflows, assets, emergency contacts, dependents, and notes.

Personal fields are grouped into cards. Several cards use the same `Редактировать` label. Locate the card by heading, then scope the edit link to it. Do not use the first or nth `Редактировать` globally. Field-group edit routes have the pattern `/people/:id/field_groups/:group_id/edit`; discover the group ID from the scoped verified link rather than hard-coding it.

Treat the profile header as authoritative for the open employee. On compensation, documents, notes, dependents, emergency contacts, and leave pages, read only the requested row/card and avoid copying unrelated sensitive values.

## Profile actions

The `Действия` menu may expose:

- request information change: `/people/:id/change_requests/new`
- reset password: `/people/:id/reset_password`
- send system invitation: `/people/:id/welcome_letter`
- assign absence policies: `/people/:id/leave_types/new`
- assign workflow: `/people/:id/workflows/new`
- onboarding workflow assignment
- Google Workspace user creation: `/integrations/gsuite_users?id=:id`

Opening the menu is read-only. Do not follow or submit any of these actions during discovery. For a requested action, verify the profile identity, inspect the destination form, summarize the exact change, and apply the confirmation rules from `SKILL.md` and the Chrome skill.

`/people/new` is the new-hire form. Creating a profile can send invitations or trigger workflows depending on form choices. Verify identity, work email, hire date, legal entity, status, position/department/location/manager, policies, and invitation/workflow toggles before submission. Do not invent missing employment data.

## Lifecycle dashboards

- Onboarding: `/processes/onboarding`
- Probation: `/processes/probation`
- Offboarding: `/processes/offboarding`

Each dashboard has a searchbox `Поиск по имени...` and a `Фильтр` button. Use them before reading cards.

Onboarding cards can show employee, position, start date, manager, assigned workflow, action totals, and completion totals. Probation cards show the probation end date and manager. Offboarding cards show end date, manager, assigned workflow, completion totals, overdue-task count, and selected outstanding tasks with assignees and dates.

For an audit, report the visible status and dates as facts; do not infer that a person passed probation or should be terminated. For overdue work, distinguish the employee associated with the process from the task assignee.

The lifecycle dashboards are authoritative for workflow assignment, action totals, completion progress, and overdue indicators. Employee/API data can supplement dates and status but does not replace the dashboard's workflow state. Opening a process card is read-only; assigning, starting, completing, or changing a workflow is consequential.

## Teams and organization chart

- Teams: `/teams`
- Organization chart: `/people/chart?view=chart`

Use `/teams` for membership/lead information and the chart for visual reporting lines. Search/filter or zoom to the relevant branch. If a line is ambiguous, verify it on the employee Work tab. Team creation, membership, and manager changes can affect permissions, workflows, and reporting; inspect dependencies and confirm exact members.

## Leave and company calendar

- Company calendar: `/company/calendars`
- Request absence: `/leave_requests/new`
- Employee absence: `/people/:id/leave`

Use the calendar for overlap/company context and the employee page for balances, policies, and history. Before a request, verify employee, leave type/policy, amount/unit, dates, partial-day settings, comment/attachment, overlaps, and approval route. Submission is not proof of approval. Approve/reject/withdraw requires the exact request and current state.

## Other Core HR routes

- New hire: `/people/new`

The global `Быстрое добавление` menu includes `Запросить отсутствие` and `Найм`. Prefer direct routes when the destination is known. Opening the menu is safe; selecting an item starts a form but does not authorize submission.
