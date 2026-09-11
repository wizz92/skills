# Inbox, forms, tasks, documents, assets, knowledge, and workflows

## Home and inbox

- Home: `/`
- Inbox/notifications: `/inbox`

Use these only for feed widgets, announcements, pending items, or notifications. The home page is high-noise and can expose unrelated people/events. Read the named widget or notification only. Marking read, acknowledging, reacting, commenting, or following a notification action can change state; do not do so during discovery.

## Forms and requests

- Requests/forms: `/forms/company` (`/forms` redirects here)

Use the visible request type and current status. Before opening or submitting, verify requester/employee, form definition, approvers, required fields, attachments, and whether submission starts a workflow. General forms are UI-only. A draft is not submitted, and a submitted request is not approved.

## Tasks

- Landing: `/tasks` (currently redirects to `/company/tasks`)
- Company: `/company/tasks`
- Team: `/team/tasks`
- Mine: `/my/tasks`
- Completed company tasks: `/company/tasks?filter=completed`
- New task: `/tasks/new`

Observed controls include `Поиск...`, `Фильтр`, `Экспорт`, tabs `Компания`, `Команда`, `Мои`, and statuses `Открытые` / `Завершенный`. Columns expose task name, assignee, related employee/object, start/due/created dates.

Filter by status/assignee/date and search by name before reading rows. Preserve the distinction between assignee and related employee. Opening is read-only; creating, editing, commenting, reassigning, completing/reopening, and deleting can notify people or advance workflows. Verify exact task, assignee, related object, due date, current state, and automation impact.

## Company and employee documents

- Company documents: `/documents/company` (`/documents` redirects here)
- Employee documents: `/people/:id/documents`

Use company documents for library/folder navigation and employee documents for the verified profile. Inspect filename, folder, owner/employee, visibility, version/date, and document type before preview/download/upload/move/delete. Uploading or linking transmits sensitive data; read the browser upload instructions and obtain action-time confirmation. Temporary download links and downloaded files are not permanent storage.

## Assets

- Assets: `/asset/items/company` (`/asset/items` redirects here)
- Employee assignments: `/people/:id/asset_assignments`

Filter by inventory identifier, category, status, or assignee. Verify serial/inventory value, category, current assignee, assignment/return dates, and condition before assigning, returning, or editing. Do not identify an asset by display name alone. Delete/reassign actions need dependency inspection and confirmation.

## Knowledge base

- Categories: `/knowledge_base/categories`

Navigate to the relevant category/article; do not crawl all content. Reading is non-mutating. Creating, editing, publishing, archiving, or reordering can change company-wide information; verify title, category, visibility, links/attachments, and publication state. Use API v3 only for structured reads.

## Workflows

- Definitions: `/workflows`
- New definition: `/workflows/new`
- Instance history: `/workflow_instances?criteria%5Bworkflow_definition_ids%5D%5B%5D=`
- Tags: `/workflow_tags`

The definition list shows name, action count, employee count, trigger/tags, owner, updated date, and active switch. Search by exact name. Similar inactive or `NO ACTUAL` definitions are common; verify owner, trigger, tags, target population, action count, and active state.

Inspecting a definition/instance is read-only. Editing conditions/actions, toggling active, assigning/launching, retrying/canceling instances, completing actions, or deleting can affect many employees or send notifications. Before a change, inspect dependent processes, target population, timing, recipients/content, and running instances. Never toggle a list switch during exploration.
