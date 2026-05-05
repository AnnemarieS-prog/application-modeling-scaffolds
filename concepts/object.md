# Object

## Definition

An object is a distinguishable application-level entity that can be governed.

An object is a design-level unit of responsibility. It is not necessarily identical to a database table, class, component, route, or API resource.

An object usually has one or more of the following:

- identity
- lifecycle
- access rules
- ownership or responsibility semantics
- data that may be viewed, changed, removed, imported, or exported
- optional extensions such as comments, attachments, notes, or workflow status

## Object Types

| Type | Meaning | Examples |
|---|---|---|
| Core object | Independent entity with its own lifecycle and access model | Invoice, Ticket, User, Project |
| Extension object | Parent-bound additive entity | Comment, Attachment, Note, Internal remark |
| Workflow/status extension | State model attached to an object | Draft, Submitted, Approved, Archived |
| System object | Technical or administrative entity | Audit log, Import job, Permission set |

## Modeling Rule

An object should be modeled explicitly when changes to it require separate decisions about access, ownership, lifecycle, visibility, or responsibility.

## Boundary Questions

| Question | If yes, model explicitly |
|---|---|
| Does it need its own access rules? | Likely yes |
| Does it have a lifecycle? | Likely yes |
| Can ownership or responsibility change? | Likely yes |
| Can it be listed, viewed, updated, removed, imported, or exported? | Likely yes |
| Is it only meaningful inside a parent object? | Treat as extension object |
| Is it purely derived or display-only? | Maybe not an object |

## Important Distinction

Objects are application-design concepts first. Their implementation may later map to tables, models, APIs, files, events, or multiple technical structures.
