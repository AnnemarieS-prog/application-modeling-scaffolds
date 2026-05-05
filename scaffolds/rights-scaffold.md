# Rights Scaffold

## Purpose

This scaffold defines the capability surface for an application object before implementation-level permission names, role assignments, or authorization checks are created.

It answers:

```text
What can be governed for this object?
```

It does not answer:

```text
Which role receives which rights?
```

Role assignment should happen after the object capability surface is defined.

---

## 1. Ownership and Scope Definitions

| Concept | Required definition | Default |
|---|---|---|
| Creator | Who originally created the object | Immutable audit field |
| Owner | Who currently owns / is responsible | Used for `own` rights |
| Assignee | Who is handling the object | Optional; distinct from owner |
| Team/unit owner | Group responsibility | Optional |

Core rule:

```text
own = current owner / responsible party
own != creator, unless explicitly defined
```

---

## 2. Starting Conditions

| Creation path | Required rule | Common default |
|---|---|---|
| Manual create | Creator + owner assignment | `creator = acting user`, `owner = creator` |
| Create for another | Creator vs owner split | `creator = acting user`, `owner = target user` |
| Import | Ownership of imported records | importing user, mapped owner, team, or system |
| System-generated | Creator + owner | `creator = system`, `owner = responsible user/team/system` |
| Copy/duplicate | Ownership reset or carry-over | `creator = copying user`, `owner = copying user` |

---

## 3. General Object Rights Matrix

| Category | Right | Own | Any | Applicable? | Notes |
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

---

## 4. Extension Blocks

### 4.1 Workflow / Status Extension

Attach only if the object has meaningful status or workflow behavior.

| Category | Right | Own | Any | Applicable? | Notes |
|---|---|---:|---:|---:|---|
| Workflow | See status | ✓ | ✓ | ☐ | |
| Workflow | Set status | ✓ | ✓ | ☐ | |
| Workflow | Transition status | ✓ | ✓ | ☐ | |

Workflow configuration:

| Rule | Purpose | Defined? | Notes |
|---|---|---:|---|
| Status list | All possible states | ☐ | |
| Visible statuses | Which roles may see which statuses | ☐ | |
| Assignable statuses | Which roles may directly set which statuses | ☐ | |
| Allowed transitions | Valid source -> target changes | ☐ | |
| Terminal statuses | Locked/final states | ☐ | |
| Hidden statuses | Excluded from UI | ☐ | |

### 4.2 Generic Extension Object Block

Use for parent-bound additive objects such as comments, notes, attachments, internal remarks, or reactions.

| Category | Right | Own | Any | Applicable? | Notes |
|---|---|---:|---:|---:|---|
| Read | Read | ✓ | ✓ | ☐ | |
| Write | Create | — | ✓ | ☐ | |
| Write | Update | ✓ | ✓ | ☐ | |
| Soft removal | Soft-delete | ✓ | ✓ | ☐ | |
| Recovery | Restore | ✓ | ✓ | ☐ | |
| Hard removal | Hard-delete | ✓ | ✓ | ☐ | |

Parent-scoped rule:

```text
CanUseExtension =
  CanReadParent
  AND HasExtensionRight
```

`extension.read.any` means “read all extension entries attached to accessible parent objects,” not “read all extension entries globally.”

---

## 5. Ownership Rules

| Rule | Required decision |
|---|---|
| Valid owner targets | |
| Reassignment | |
| Self-assignment | |
| Unassignment | |
| Status restrictions | |
| Audit/logging | |

---

## 6. Rights-Assignment UX Scaffolding

This section defines how a role configuration UI should guide, warn, suggest, or block rights combinations.

| Right being assigned | UI scaffold | Type |
|---|---|---|
| Update | Prompt/check for Detail | |
| Soft-delete | Prompt/check for Detail | |
| Restore | Prompt/check for Detail + deleted visibility | |
| Hard-delete | Prompt/check for Detail + destructive warning | |
| Export | Prompt/check for List and/or Detail | |
| Assign owner | Prompt/check for Detail (+ Update optionally) | |
| Import | Show as high-impact/system-level action | |
| Workflow rights | Require status visibility + transition config | |
| Extension rights | Require parent Detail + extension Read | |

Scaffolding types:

| Type | Meaning |
|---|---|
| Hard-required | UI blocks invalid combinations |
| Advisory | UI warns but allows override |
| Auto-suggested | UI proposes companion rights |
| Informational | UI explains runtime dependency only |
