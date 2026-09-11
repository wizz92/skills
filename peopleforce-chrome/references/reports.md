# PeopleForce reports and exports

## Entry points

- Company reports: `/reports`
- Custom reports: `/reports/my`

Use the catalog only when the report is unclear. For a known report, open its direct route, apply the narrowest date/population filters, and read the displayed total, table, chart, or export.

## General and audit

- Task progress: `/reports/general/tasks`
- Security audit: `/reports/general/security`
- System log: `/reports/general/system_log`
- Employee data changes: `/reports/hr/employee_audits`

## Core HR

- Headcount: `/reports/hr/headcount`
- Turnover: `/reports/hr/turnover`
- Tenure: `/reports/hr/tenure`
- Custom employee fields: `/reports/hr/custom_fields`
- Employment status history: `/reports/hr/employment_status_histories`
- Career change history: `/reports/hr/job_history`
- Monthly payroll: `/reports/hr/payroll`
- Compensation history: `/reports/hr/salary_histories`
- Working hours: `/reports/hr/working_hours`
- Leave used: `/reports/hr/leave_used`
- Leave request history: `/reports/hr/leave_requests`
- Leave balances: `/reports/hr/leave_balance`
- Leave policies: `/reports/hr/leave_policy`
- Assets: `/reports/hr/assets`
- Mood: `/reports/hr/mood`
- Birthdays/anniversaries: `/reports/hr/celebrations`
- Dependents: `/reports/hr/dependents`
- Emergency contacts: `/reports/hr/emergency_contacts`

Age, gender, gender-pay-gap, compensation, contacts, dependents, security, and performance reports are especially sensitive. Open only when explicitly relevant and avoid small cohorts that expose individuals.

## Perform

- 1:1 status: `/reports/perform/one_on_ones`
- Goal ownership/status: `/reports/perform/ownership`
- Company KPI: `/reports/perform/key_performance_indicators`
- Development plans: `/reports/perform/development_plans`

## Recruit

- Pipeline funnel: `/reports/recruit/pipeline_funnel`
- Pipeline statistics: `/reports/recruit/pipeline_statistics`
- Candidate sources: `/reports/recruit/candidate_sources`
- Vacancy funnel: `/reports/recruit/vacancy_funnel`
- Time to hire: `/reports/recruit/time_to_hire`
- Time to fill: `/reports/recruit/time_to_fill`
- Time to disqualify: `/reports/recruit/time_to_disqualify`
- Time in stage: `/reports/recruit/time_in_stage`
- Recruiter activities: `/reports/recruit/activities`

## Reliable report workflow

1. Confirm the metric definition and whether dates mean event, effective, employment, or report period.
2. Set date, status, legal entity, department/division/location, manager, employee/vacancy, and other requested filters before reading totals.
3. Record active filter labels and visible population/count. Defaults may not mean all employees or the intended period.
4. Treat UI totals/charts as authoritative for a built-in metric. API raw data can support custom calculations but may use different definitions or role scope.
5. Use displayed totals and targeted rows for pagination. Do not dump all pages into context. Export large analysis only after verifying columns, filters, format, and sensitive scope.
6. Verify the downloaded filename/format and, when practical, row count/period against the UI. Do not change custom report definitions, saved views, or shared filters unless requested.

Tenant behavior observed: many reports combine summary KPI cards, a chart with `Zoom Out`, and a detailed table; the `Фильтр (N)` label reveals the number of active filters. Recruit time reports may expose a separate date-range control. Read the active period and filters before interpreting cards, and use table columns to explain the metric rather than copying every row.
