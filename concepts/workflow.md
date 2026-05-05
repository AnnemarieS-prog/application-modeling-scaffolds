# Workflow and Status

## Definition

Workflow/status describes the state model attached to an object.

Workflow is treated as an optional extension block, not as mandatory base object behavior. Not every object has a meaningful state machine.

## Core Concepts

| Concept | Meaning |
|---|---|
| Status | Current state of an object |
| Visible status | Status a role may see |
| Assignable status | Status a role may directly set |
| Transition | Allowed source -> target status change |
| Terminal status | State that normally cannot change further |
| Hidden status | State excluded from UI, filters, or detail views for a role |

## Workflow Rights

| Category | Right | Own | Any |
|---|---|---:|---:|
| Workflow | See status | ✓ | ✓ |
| Workflow | Set status | ✓ | ✓ |
| Workflow | Transition status | ✓ | ✓ |

## Configuration Matrixes

A workflow extension normally requires:

- status list
- status visibility matrix
- assignable status matrix
- transition matrix
- terminal/hidden status rules

## Important Distinction

| Permission | Meaning |
|---|---|
| Update | Modify ordinary object content |
| Set status | Directly assign a workflow state |
| Transition status | Move along an allowed workflow edge |

`update` should not automatically imply approval, rejection, publication, archiving, or other workflow authority.
