# Actor

## Definition

An actor is any principal that can interact with the application — either with the platform itself, or with objects within it.

Actor type and scope are distinct. Type describes what kind of principal the actor is. Scope describes the reach of an actor's access — its meaning varies depending on which layer the interaction occurs at.

## Layer 1 — Platform-level actor types

| Actor type | Description |
|---|---|
| System | Any action performed by internal code — background jobs, seed data, scheduled tasks, internal services |
| Unauthenticated individual | A person accessing the application without a registered identity |
| Authenticated individual | A registered, logged-in user |
| External automated system | Third-party integrations, external APIs, webhooks |

## Layer 2 — Object relationship

An actor may hold a relationship to a specific object. That relationship influences which rights apply to them for that object. The set of possible relationships is not fixed — it depends on the object and the application.

| Relationship | Description |
|---|---|
| Owner | The actor responsible for the object; typically holds the broadest rights over it |
| Creator | The actor who originally created the object; immutable once set |
| Assignee | An actor explicitly assigned to the object, typically to act on or progress it |
| Editor | An actor with rights to modify the object's content |
| Viewer | An actor with read-only access to the object |

## Layer 3 — Grouping and bridge to roles

Actors can be grouped. A group shares a defined set of rights at a defined scope. This is the foundation of roles.

Scope at this layer answers: across which objects do a role's rights apply? Scope can be defined by object relationship, by boundary, or by object type.

Relationship names from Layer 2 may reappear as role names — the relationship an actor holds to an object naturally informs what role they occupy.

Common standard roles that naturally emerge from this structure:

| Role | Typical scope |
|---|---|
| System administrator | Platform-wide; acts on any object |
| Manager | Broad scope within a defined boundary |
| Support agent | Read and limited action across all objects |
| Standard user | Scoped to objects they own or are assigned to |
| Viewer | Read-only across a defined scope |
| Moderator | Oversight rights across a defined scope |

Role definition — what rights a role holds and at what scope — is covered in `role.md`.
