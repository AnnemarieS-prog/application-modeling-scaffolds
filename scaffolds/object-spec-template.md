# Object Specification Template

## Object Name

Name the application-level object.

## Object Type

| Field | Value |
|---|---|
| Type | Core object / Extension object / System object / Other |
| Parent object | |
| Extension blocks | Workflow / Comments / Attachments / Notes / Other |

## Object Definition

Describe what this object represents at the application-design level.

```text
This object represents...
```

## Object Boundary

Define what belongs to this object and what does not.

| In scope | Out of scope |
|---|---|
| | |

## Ownership Model

| Concept | Definition for this object |
|---|---|
| Creator | |
| Owner | |
| Assignee | |
| Team/unit owner | |

Core rule for this object:

```text
own =
```

## Starting Conditions

| Creation path | Rule for this object |
|---|---|
| Manual create | |
| Create for another | |
| Import | |
| System-generated | |
| Copy/duplicate | |

## Supported Base Rights

| Category | Right | Own | Any | Supported? | Notes |
|---|---|---:|---:|---:|---|
| Read | List | ✓ | ✓ | ☐ | |
| Read | Detail | ✓ | ✓ | ☐ | |
| Write | Create | — | ✓ | ☐ | |
| Write | Update | ✓ | ✓ | ☐ | |
| Soft removal | Soft-delete | ✓ | ✓ | ☐ | |
| Recovery | Restore | ✓ | ✓ | ☐ | |
| Hard removal | Hard-delete | ✓ | ✓ | ☐ | |
| Data extraction | Export | ✓ | ✓ | ☐ | |
| Data ingestion | Import | — | ✓ | ☐ | |
| Ownership | View owner | ✓ | ✓ | ☐ | |
| Ownership | View creator | ✓ | ✓ | ☐ | |
| Ownership | Assign owner | ✓ | ✓ | ☐ | |
| Administration | Manage permissions | — | ✓ | ☐ | |

## Extension Blocks

### Workflow / Status

| Question | Answer |
|---|---|
| Does this object have workflow/status behavior? | |
| Status list defined? | |
| Visibility matrix defined? | |
| Assignable status matrix defined? | |
| Transition matrix defined? | |
| Terminal/hidden states defined? | |

### Parent-Bound Extensions

| Extension | Attached? | Notes |
|---|---:|---|
| Comments | ☐ | |
| Attachments | ☐ | |
| Notes | ☐ | |
| Internal remarks | ☐ | |
| Other | ☐ | |

## Ownership Rules

| Rule | Decision |
|---|---|
| Valid owner targets | |
| Who may reassign? | |
| Self-assignment allowed? | |
| Unassignment allowed? | |
| Status restrictions? | |
| Audit/logging required? | |

## Rights-Assignment UX Scaffolding

| Right / area | Scaffolding behavior | Type |
|---|---|---|
| Update | | |
| Soft-delete | | |
| Restore | | |
| Hard-delete | | |
| Export | | |
| Import | | |
| Assign owner | | |
| Workflow rights | | |
| Extension rights | | |

## Open Decisions

| Decision | Owner | Status | Notes |
|---|---|---|---|
| | | | |
