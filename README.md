# System Design Scaffolds

A lightweight collection of reusable scaffolds for structuring application-level design decisions.

This repository provides templates and concept notes to help make non-trivial design choices explicit before they are encoded in implementation.

It is documentation-only and not tied to any specific framework, language, or architecture.

---

## Purpose

Many application features start simple but quickly accumulate implicit decisions:

- who is responsible for what
- what actions are allowed and under which conditions
- how behaviour changes over time
- how related pieces interact

If these decisions remain implicit, they tend to diverge across features and become difficult to reason about later.

This repository provides structured scaffolds to surface and standardise those decisions early.

---

## When to Use This

Use these scaffolds when a feature or domain area stops being trivial and requires deliberate design.

Typical signals:

- behaviour is no longer obvious from the feature description alone
- multiple reasonable interpretations exist
- similar concepts appear in multiple places and need consistency
- decisions would otherwise be made ad hoc during implementation
- you find yourself explaining the same rules repeatedly

The goal is not to document everything, but to make **relevant design decisions explicit and consistent**.

---

## What This Helps Avoid

- implicit and inconsistent behaviour across features
- conflating distinct concepts (e.g. creator vs owner vs assignee)
- access rules emerging indirectly from implementation
- lifecycle or state behaviour being scattered or unclear
- extensions behaving inconsistently depending on context
- needing to reverse-engineer design from code later

---

## Structure

```text
/concepts/
  object.md
  ownership.md
  workflow.md

/scaffolds/
  object-spec-template.md
  rights-scaffold.md
```

### Concepts

Define shared terminology and core ideas.

They provide the vocabulary used by the scaffolds, but do not prescribe specific implementations.

### Scaffolds

Provide structured templates for defining behaviour.

They are intended to be copied, adapted, and filled out in the context of a specific feature or system.

---

## How to Use

A typical flow:

1. Identify a feature or domain area that requires explicit design
2. Select a relevant scaffold (or combine multiple)
3. Fill it out with concrete decisions
4. Use the result as input for implementation or further discussion

The scaffolds are intentionally minimal and flexible. They are meant to guide thinking, not enforce a process.

---

## Scope

This repository focuses on **application-level modelling and design structure**.

It deliberately avoids:

- implementation details
- permission constants or code-level naming
- database schemas
- framework-specific patterns

It is meant to sit *before* those concerns.

---

## Notes

- Not every feature requires a scaffold
- Not every scaffold needs to be fully filled out
- The goal is clarity, not completeness

Use this as a tool when it adds value, and ignore it when it doesn’t.

---

## Exploration Roadmap

See [EXPLORATION.md](EXPLORATION.md) for directions under consideration.

---

## Development Notes

This repository was developed iteratively with tool assistance.
All concepts and structures are curated and validated for consistency.
