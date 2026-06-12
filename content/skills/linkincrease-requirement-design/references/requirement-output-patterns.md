# Requirement Output Patterns

Use this reference when writing or heavily rewriting Linkincrease iteration PRDs.

## Design Bias

Write for implementation, review, and testing. The output should help product, development, QA, operations, and product success quickly locate what changes, where it changes, who can use it, and how it should be accepted.

Prefer this order:

1. Source basis and scope.
2. Deliverable feature list.
3. Product-end-specific detailed design.
4. Shared rules.
5. Acceptance criteria and testing focus.
6. Risks and questions.

Keep analysis short unless the user explicitly asks for exploration.

## Standard PRD Skeleton

```markdown
# {Feature Name} Requirement Document

## 1. Source Basis and Scope

| Item | Content |
|---|---|
| Source | |
| Target users | |
| Product ends | |
| Impacted objects | |
| V1.0 scope | |
| Non-goals | |

## 2. Deliverable Feature List

| ID | Feature | End | Module/Page | User Role | Priority | Dependency | Status |
|---|---|---|---|---|---|---|---|

## 3. Existing Rules and Impact Summary

## 4. Product-End Detailed Design

### 4.1 运营端

#### 4.1.1 Entry and Menu
#### 4.1.2 List Page
#### 4.1.3 Detail Page
#### 4.1.4 Configuration and Permission
#### 4.1.5 Logs and Audit

### 4.2 贸易端

#### 4.2.1 Entry and Page Location
#### 4.2.2 List Interaction
#### 4.2.3 Detail Interaction
#### 4.2.4 Form, Work Order, and Approval Rules
#### 4.2.5 Empty, Error, and No-Permission States

### 4.3 采集端

#### 4.3.1 Entry and Task Context
#### 4.3.2 Task Detail Interaction
#### 4.3.3 Form Filling and Submission
#### 4.3.4 Offline, Attachment, and Sync Rules
#### 4.3.5 Empty, Error, and No-Permission States

## 5. Shared Business Rules

### 5.1 Object and Data Model
### 5.2 Data Flow
### 5.3 Permission and Data Fence
### 5.4 State and Lifecycle
### 5.5 Notification and Automation
### 5.6 Audit, Logs, and History
### 5.7 Import, Export, and Compatibility

## 6. Acceptance Criteria

| ID | Scenario | Given | When | Then | Priority |
|---|---|---|---|---|---|

## 7. Testing Focus

## 8. Risks and Open Questions
```

Remove sections that do not apply, but keep the product-end detailed design continuous.

## Continuity Rules

- Do not write 贸易端 design in one section and then return to 贸易端 several headings later.
- If a shared rule affects multiple ends, write the concrete end behavior first, then summarize the shared rule later.
- If the same object appears in multiple ends, describe the user's page behavior in each end and put object-level rules in Shared Business Rules.
- If a feature has only one end, omit unused end sections instead of keeping empty headings.
- If V1.0 and later phases differ, label feature IDs and section titles with `V1.0` or `Later`.

## Deliverable Feature List Rules

Every feature row should be small enough for development or QA to track. Split a feature when:

- It belongs to a different product end.
- It changes a different page or entry.
- It has different permission or state rules.
- It can be released or tested independently.

Use stable IDs:

```text
OP-001 运营端
TR-001 贸易端
CO-001 采集端
SR-001 Shared rule
```

## Acceptance Criteria Rules

Use acceptance criteria to turn product decisions into testable behavior.

Each criterion should include:

- Scenario.
- Preconditions or permission.
- User action or system trigger.
- Expected UI/data/state/log result.
- Exception handling when relevant.

Prefer concrete examples over generic statements such as "works normally".
