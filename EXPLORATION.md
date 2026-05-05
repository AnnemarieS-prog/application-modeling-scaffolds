# Exploration Roadmap

Directions worth developing further. Not commitments — areas where structured scaffolds may add similar value to what exists today.

---

## Role modelling

The current scaffolds define what can be governed (capability surface) and who is responsible (ownership). They do not address who is allowed to act — role assignment.

A role scaffold would avoid prescribing specific role names and instead provide structure for:

- **Actor types** — what kinds of principals exist (human user, team/group, system actor, external party)
- **Scope levels** — which objects a role can act on (own, assigned, team, tenant, any)
- **Rights profiles** — which capabilities from the rights scaffold this role holds
- **Elevation rules** — which roles can grant or revoke rights for other roles
- **Scope override conditions** — when a role may act outside its default scope

A role scaffold would take the rights-scaffold output as input. Role definition (what this role is) remains separate from role assignment (which users hold this role).

---

## Visibility as a distinct concept

The rights matrix separates `List` from `Detail`, but visibility is not yet defined as a concept. Visibility governs whether an object is discoverable (appears in search or listings) independently from whether its content is accessible. This distinction matters for objects that should be known to exist but not fully readable by all actors.

---

## Cross-object relationships and constraints

How objects reference, depend on, or constrain each other. Relevant when access or lifecycle of one object is affected by the state of another, or when consistency rules span object boundaries.

---

## Validation and data consistency rules

Constraints on object content beyond structure — field-level rules, conditional requirements, cross-field dependencies. Useful when validation logic becomes complex enough to require explicit design before implementation.

---

## Lifecycle patterns

Objects with richer lifecycle than a simple status workflow — archival, expiry, versioning, revival. Relevant when terminal states have conditions, or when objects move between active and inactive across time.

---

## Further areas

Potentially worth structured treatment as needs emerge:

- multi-tenant and boundary modelling
- audit and change tracking patterns
- bulk operations beyond import/export
- synchronisation and state propagation
- conflict resolution and concurrency
