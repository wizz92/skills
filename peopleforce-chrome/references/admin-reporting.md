# Settings, security, imports, and integrations

Use this reference only for tenant administration. For tasks/workflows use [operations.md](operations.md); for reports use [reports.md](reports.md).

## Find a setting

Start at `/settings` only when the destination is unclear; its search field is `Поиск...`. For a known setting, use the direct route.

### General and organization

- General: `/settings/general`
- Alerts: `/settings/alerts`
- Integrations: `/settings/integrations`
- Webhooks: `/settings/webhooks/endpoints`
- Imports: `/settings/imports`
- Exports: `/settings/exports`
- Billing/plan: `/settings/billing/plan`
- Home page: `/settings/home`
- Calendars: `/settings/calendars`
- Positions: `/settings/positions`
- Seniority: `/settings/seniorities`
- Departments: `/settings/departments`
- Divisions: `/settings/divisions`
- Locations: `/settings/locations`
- Holiday policies: `/settings/holiday_policies`
- Employment types: `/settings/employment_types`
- Genders: `/settings/genders`
- Job catalog: `/settings/job_profiles`
- Skills: `/settings/skills`
- Forms: `/settings/forms`
- Groups: `/settings/groups`

### Core HR

- Leave policies: `/settings/leave/types`
- Work schedules: `/settings/working_patterns`
- Classic onboarding: `/settings/onboarding/workflows`
- Classic offboarding: `/settings/offboarding/workflows`
- Probation policies: `/settings/probation_policies`
- Termination reasons: `/settings/termination_reasons`
- Termination types: `/settings/termination_types`
- Document folders: `/settings/documents/folders`
- Employee field groups: `/settings/employee_field_groups`
- Asset fields: `/settings/asset_fields`
- Asset categories: `/settings/asset_categories`

### Recruit and Perform

- Career sites: `/settings/recruitment/career_sites`
- GDPR: `/settings/recruitment/gdprs`
- Vacancy fields: `/settings/recruitment/vacancy_fields`
- Candidate fields: `/settings/recruitment/applicant_fields`
- Vacancy pipelines: `/settings/recruitment/pipelines`
- Disqualification reasons: `/settings/recruitment/disqualify_reasons`
- Candidate sources: `/settings/recruitment/sources`
- Scorecards: `/settings/recruitment/scorecards`
- Email templates: `/settings/recruitment/email_templates`
- Interview templates: `/settings/recruitment/interview_templates`
- Offer templates: `/settings/recruitment/offer_templates`
- Resume templates: `/settings/recruitment/resume_templates`
- Candidate tags: `/settings/recruitment/applicant_tags`
- Contracts: `/settings/recruitment/contracts`
- 1:1 types/templates: `/settings/performance/one_on_one_types`, `/settings/performance/one_on_one_templates`
- Competencies: `/settings/performance/competencies`
- Development-plan types: `/settings/performance/development_plan_types`
- Objective tags: `/settings/performance/objective_tags`
- Segments: `/settings/segments`
- Rating scales: `/settings/scales`

### Security and payroll

- Compensation types: `/settings/payrolls/compensation_types`
- Roles and permissions: `/settings/permissions`
- Authentication: `/settings/authentications`
- API keys: `/settings/api_keys`

## Administration workflow

1. Inspect current value, status, owner, scope, and dependent objects. Scope repeated edit/delete/toggle controls by exact row/item name.
2. For dictionaries, normalize/search duplicates and inspect employee records, history, templates, workflows, reports, and integrations that reference the item before create/rename/delete.
3. For forms/templates, onboarding/offboarding, leave/probation, recruitment pipelines, review/1:1, and objective tags, identify active definitions and processes that consume the setting.
4. Imports need source format, mapping, preview/errors, duplicate policy, exact row count, and rejected-row handling. Never start an import during exploration.
5. Exports need explicit dataset, filters, columns, format, and storage destination. Do not export all HR data for a narrow question.
6. Integrations/webhooks need destination, data scope, authentication, owner, failure behavior, signing secret handling, and notification impact. Do not activate or test-send sensitive payloads during discovery.
7. Roles, authentication, and API keys affect access. Creating/assigning/disabling/deleting credentials, changing role populations/fields, SSO/authentication, or permissions is security-sensitive and requires the exact delta and final confirmation.

Tenant-specific actions observed: `/settings/api_keys/new` creates a key; `/settings/webhooks/endpoints/new` creates a webhook; imports expose `/settings/imports/history` and `/settings/imports/new`; people-data settings can create a group, table, or field; pipeline rows can be made default. "Make default" changes all future vacancy behavior and is not an inspection action.

Do not save organization-wide settings merely because the page is open. After an authorized change, verify the row/value and affected behavior without exposing secrets.
