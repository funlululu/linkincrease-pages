# Linkincrease Product Success Checklists

Use these checklists only when the task requires concrete execution detail.

## Customer Discovery

Ask or infer:

- Customer type: brand owner, trading company, sourcing agency, supplier, service provider, or mixed.
- Business scope: supplier governance, factory admission, order tracking, audit/QC, CAP, material/product library, reporting.
- Current tools: Excel, ERP, email, IM, Teambition/other docs, internal systems.
- Pain points: data scattered, unclear responsibility, supplier visibility, factory compliance, delayed order progress, weak audit trail.
- Success outcome: faster onboarding, fewer manual follow-ups, traceable approvals, accurate factory list, visible CAP closure.

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
- Service providers see only assigned audits/CAP tasks.
- QC/field staff can submit work orders but should not see internal commercial or audit-sensitive fields unless required.
- Management viewers can see dashboards without write access.
- External users cannot infer other suppliers/factories through views, filters, exports, or notifications.

## Scenario Patterns

### Supplier and Factory Governance

Recommended design:

- Supplier library and factory library as master data.
- Factory admission FlowSpace for supplier-submitted factory applications.
- Audit FlowSpace for social responsibility, quality, or qualification checks.
- CAP FlowSpace for issue correction.
- Order FlowSpace references approved factory records.

Critical data flow:

```text
Supplier submits factory -> brand reviews -> audit if needed -> approved factory writes back to resource library -> order references factory -> audit/CAP updates factory risk.
```

### Order Tracking

Recommended design:

- Order FlowSpace as the process container.
- Main form records order header.
- Milestones represent order stages.
- Work orders collect production, inspection, shipping, and exception progress.
- Factory field references factory library.
- Dashboards monitor overdue orders, pending tasks, factory usage, and exceptions.

### Audit/QC/CAP

Recommended design:

- Audit/QC FlowSpace records audit plan, field collection, report upload, and conclusion.
- CAP FlowSpace records issue item, owner, deadline, evidence, review result, and closure.
- Audit result and CAP status write back to factory library.

## Dashboard Checklist

Operational dashboards:

- Pending tasks by owner.
- Overdue orders.
- Upcoming audit dates.
- CAP overdue count.
- Factory admission pending count.
- Failed or pending approvals.

Management dashboards:

- Supplier performance.
- Factory risk distribution.
- Order delivery health.
- Audit pass/fail trend.
- CAP closure rate and average closure time.
- Resource library completeness.

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
