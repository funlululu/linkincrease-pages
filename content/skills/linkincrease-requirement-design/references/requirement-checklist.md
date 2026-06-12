# Requirement Checklist

Use this checklist when drafting or reviewing Linkincrease requirements.

## Classification

- Which product end is affected: 运营端, 贸易端, 采集端, or public capability?
- Which module owns the entry?
- Which existing knowledge page should be updated?
- Is this a new capability, rule adjustment, permission change, state change, data change, or copy change?
- Is the input from current requirements (`source:thoughts-v2-current`) or historical product reference (`source:product-docs-legacy`)?
- Does this request require product strategy, user role, metrics, roadmap, or priority context?

## Business Scope

- Object: FlowSpace, order, milestone, work order, resource library, template, dashboard, report, automation, message, log.
- User role: platform operator, team owner, team admin, normal member, collaboration team member, collector.
- Entry: menu, list, detail page, settings, modal, mobile page, external link, background job.
- Operation: view, create, edit, delete, batch, import, export, copy, sync, assign, approve, cancel, restart.
- Strategic fit: product positioning, target user, value proposition, stage goal, metric, roadmap priority.

## Required Rules

- Permission: team permission, FlowSpace role, collaborative FlowSpace role, resource permission, dashboard/report permission, data fence.
- State: draft, active, inactive, processing, completed, canceled, deleted, expired, failed.
- Data: field defaults, required fields, validation, old data compatibility, snapshot, sync range, conflict handling.
- Notification: station message, realtime message, email, SMS, task center, assignment notice.
- Audit: operation log, dynamic, history record, tracking record, system execution log.
- Import/export: template, fields, async task, failure reason, permission and data range.
- Exception: no permission, missing data, invalid state, duplicate operation, import failure, sync failure.
- Multi-end difference: whether 运营端, 贸易端, and 采集端 behave differently.

## Output Structure

- Does the PRD start with scope, non-goals, and a deliverable feature list?
- Are 运营端, 贸易端, and 采集端 details grouped continuously instead of scattered across distant sections?
- Does each feature point map to a concrete page, entry, operation, permission, state, data rule, and log/audit requirement when applicable?
- Are shared rules separated from end-specific UI and interaction behavior?
- Are V1.0 and later-phase capabilities clearly separated?
- Are acceptance criteria specific enough for QA and development to verify?

## Review Output

When reviewing, produce:

- Missing requirement details.
- Potential conflicts with existing knowledge.
- Source authority conflicts, especially historical product docs versus latest requirements.
- Impacted knowledge pages.
- Questions requiring product confirmation.
- Suggested PRD sections or exact additions.
- Testing focus points when useful.
- Structure issues that make the document hard to implement, especially repeated or scattered end/module sections.

## Avoid

- Do not introduce synonyms for existing terms.
- Do not write unconfirmed assumptions as final rules.
- Do not ignore permissions, states, logs, or historical data impact.
- Do not change source filenames that are used for traceability.
