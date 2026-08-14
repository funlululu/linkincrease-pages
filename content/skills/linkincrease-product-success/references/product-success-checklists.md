# Linkincrease Product Success Checklists

Use these checklists only when the task requires concrete execution detail.

Do not apply every checklist to every product-success question. Product success work should first diagnose the customer's business problem, then choose the smallest relevant checklist sections. Capability names in this file are options, not defaults.

## Checklist Selection

Before using detailed checklists, classify the request:

| Request type | Use sections | Do not automatically add |
| --- | --- | --- |
| Customer discovery | Customer Discovery, selected capability questions | CAP, dashboards, automation, integration unless evidenced |
| Onboarding/configuration | Master Data, FlowSpace Template, Permission, Onboarding Runbook | Audit/QC/CAP unless the customer scope includes quality/compliance整改 |
| Troubleshooting | Permission, FlowSpace Template, Knowledge Capture if recurring | New dashboards or supplier-governance方案 unless needed |
| Dashboard/value review | Dashboard Checklist, metric definitions | CAP closure metrics unless corrective-action workflows are in scope |
| Scenario solution | Only the matching Scenario Pattern | Other scenario patterns just because they appear nearby |
| Professional operations方案 | Industry scenario page, matching customer方案, capability boundary | Pure feature list without industry reasoning |
| Knowledge capture | Knowledge Capture Checklist | Product-rule updates unless confirmed |

If evidence is weak, ask for context or state assumptions instead of expanding the方案.

## Customer Discovery

Ask or infer:

- Customer type: brand owner, trading company, sourcing agency, supplier, service provider, or mixed.
- Business scope: supplier governance, factory admission, order tracking, audit/QC when relevant, exception handling, corrective-action/CAP only when justified, material/product library, reporting.
- Current tools: Excel, ERP, email, IM, Teambition/other docs, internal systems.
- Pain points: data scattered, unclear responsibility, supplier visibility, factory compliance, delayed order progress, weak audit trail.
- Success outcome: faster onboarding, fewer manual follow-ups, traceable approvals, accurate factory list, visible issue or corrective-action closure when relevant.

Capability-fit questions:

- Is this mainly a master-data problem, a process-tracking problem, a permission problem, a reporting problem, a troubleshooting problem, or a knowledge-capture problem?
- Which capability is necessary for the next action, and which capability is only a possible later extension?
- Which common supply-chain terms should be avoided because the customer did not provide evidence for them?

## Master Data Checklist

For each resource library, define:

- Name and purpose.
- Unique key.
- Required fields.
- Option values and status values.
- Owner and maintainer.
- Import source.
- Update frequency.
- Linked FlowSpace fields.
- Permission boundary.
- Dashboard usage.

Typical libraries:

- Supplier library.
- Factory library.
- Product/material/style library.
- Certificate/report library.
- Issue/category library.
- Service provider/QC library.

## FlowSpace Template Checklist

For each business template:

- Business objective.
- Creator role.
- Main form fields.
- Milestones.
- Work orders under each milestone.
- Work order executor.
- Approval requirement.
- Status transitions.
- Required attachments.
- Resource library references.
- Write-back target.
- Notifications.
- Logs/audit requirements.
- Dashboard fields.

## Permission Checklist

Validate:

- Brand owner administrators can manage full scope.
- Brand owner business users see assigned or authorized data.
- Suppliers see only their own orders, factories, tasks, and allowed fields.
- Factories see only assigned factory data or collection tasks.
- Service providers see only assigned audits, QC tasks, or corrective-action tasks when those workflows are in scope.
- QC/field staff can submit work orders but should not see internal commercial or audit-sensitive fields unless required.
- Management viewers can see dashboards without write access.
- External users cannot infer other suppliers/factories through views, filters, exports, or notifications.

## Scenario Patterns

### Supplier and Factory Governance

Recommended design:

- Supplier library and factory library as master data.
- Factory admission FlowSpace for supplier-submitted factory applications.
- Audit FlowSpace for social responsibility, quality, or qualification checks.
- Corrective-action/CAP FlowSpace only for audit findings, inspection defects, nonconformance,整改闭环, repeated high-risk exceptions, or compliance issue closure.
- Order FlowSpace references approved factory records.

Critical data flow:

```text
Supplier submits factory -> brand reviews -> audit if needed -> approved factory writes back to resource library -> order references factory -> audit results or justified corrective actions update factory risk.
```

### Order Tracking

Recommended design:

- Order FlowSpace as the process container.
- Main form records order header.
- Milestones represent order stages.
- Work orders collect production, inspection, shipping, and exception progress.
- Factory field references factory library.
- Dashboards monitor overdue orders, pending tasks, factory usage, and exceptions.

### Audit/QC/Corrective Action

Recommended design:

- Audit/QC FlowSpace records audit plan, field collection, report upload, and conclusion.
- Corrective-action/CAP FlowSpace records issue item, owner, deadline, evidence, review result, and closure only when the scenario requires formal整改闭环.
- Audit result and justified corrective-action status write back to factory library.

## Dashboard Checklist

Operational dashboards:

- Pending tasks by owner.
- Overdue orders.
- Upcoming audit dates.
- Corrective-action overdue count, only when corrective-action workflows are in scope.
- Factory admission pending count.
- Failed or pending approvals.

Management dashboards:

- Supplier performance.
- Factory risk distribution.
- Order delivery health.
- Audit pass/fail trend.
- Corrective-action closure rate and average closure time, only when corrective-action workflows are in scope.
- Resource library completeness.

## CAP Boundary Checklist

Do not introduce CAP unless the user request or evidence clearly indicates a corrective-action workflow.

Use CAP when:

- The customer explicitly mentions CAP,整改, corrective action, nonconformance, defect closure, root cause, or preventive action.
- Audit, QC, inspection, compliance, or factory admission findings need owner, deadline, evidence, review, and closure.
- A repeated or high-risk exception needs formal root-cause correction and verification.

Avoid CAP when:

- The task is ordinary order tracking, status updates, or task follow-up.
- The task is resource-library setup or master data maintenance.
- The task is onboarding, permission troubleshooting, dashboard design, or general customer configuration.
- A simple work order, approval, reminder, or exception record is enough.

For each metric, define:

- Data source.
- Field口径.
- Filter dimensions.
- Owner.
- Update cadence.
- Decision supported.

## Onboarding Runbook

1. Confirm customer scenario and success metrics.
2. Build team and role model.
3. Design resource libraries.
4. Prepare import templates and sample data.
5. Configure business templates.
6. Configure permissions and data fences.
7. Configure automation and notifications.
8. Configure dashboards.
9. Validate with role-based test accounts.
10. Train customer administrators and external collaborators.
11. Pilot with real data.
12. Go live.
13. Stabilize and capture issues.
14. Run 30-day value review.

## Knowledge Capture Checklist

Capture as knowledge when:

- The same issue appears more than once.
- A customer configuration becomes reusable.
- A new field/status/permission pattern is confirmed.
- A troubleshooting path is stable.
- A dashboard metric is accepted by customer management.

Include:

- Scenario.
- Configuration.
- Roles.
- Data flow.
- Validation steps.
- Known risks.
- Source or confirmation status.
